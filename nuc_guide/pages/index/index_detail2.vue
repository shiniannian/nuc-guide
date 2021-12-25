<template>
	<view>
		<view class="banner">
			<image class="banner-img" :src="end.photo"></image>
			<view class="banner-title">{{end.title}}</view>
		</view>
		<view class="article-meta">
			<text class="article-author">{{start.title}}</text>
			<text class="article-text">到</text>
			<text class="article-time">{{end.title}}</text>
		</view>
		
		<view class="article-content">
			<view style="color: #007AFF;">编号列表：</view>
			<view>一号楼（1），东区篮球场（2），十四号楼（3），广顺超市（4），十号楼（5），文涛餐厅（6），科学楼（7），瑾瑜国际会议中心（8），十一号楼（9），图书馆（10）</view>
			<view class="line"></view>
			<view class="shortest-path">
				<view style="color: #007AFF;">
					{{start.title}}到{{end.title}}的最短路径：
				</view>
				<view class="ShortestPath">
					<view class="ShortestPath-item" v-for="item in ShortestPath">
						---->{{item}}
					</view>
					<view>且长度为：{{Shortestlength}}</view>
				</view>
			</view>
			<view class="line"></view>
		  
			<view class="many-path" >
				<view style="color: #007AFF;">
					以{{start.title}}为起点，以{{end.title}}为终点，且途径{{num}}个顶点的最佳路径：
				</view>
				<view class="manySpotPath">
					<view class="manySpotPath-item" v-for="item in manySpotPath">
						------->{{item}} 
					</view>
				</view>
				<view>
					且最佳路径长度为：{{min}} 米
				</view>
			</view>
			<view class="line"></view>
			
			<view class="all-path">
				<view style="color: #007AFF;">
					{{start.title}}到{{end.title}}的所有路径：
				</view>
				
				<view>
					<view class="allPath1" v-for="allPath1 in res">
						<view v-for="item in allPath1">
							->{{item}}
						</view>
					</view>
				</view>
			</view>
			<view class="line"></view>
			<view class="jpoint">
				<view style="color: #007AFF;">
					本校园图的关节点是：
				</view>
				<view>
					{{jpoint}}
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data(){
			return{
				start:{},
				end:{},

				//所有路径算法
				map : [
					[0,0,0,0,0,0,0,0,0,0,0],
					[0,0,0,190,0,0,0,0,327,161,0],
					[0,0,0,20,0,0,0,0,0,0,0],
					[0,190,20,0,75,0,305,0,0,0,0],
					[0,0,0,75,0,177,230,0,0,0,0],
					[0,0,0,0,177,0,185,0,0,0,0],
					[0,0,0,305,230,185,0,366,370,0,0],
					[0,0,0,0,0,0,366,0,54,0,0],
					[0,327,0,0,0,0,370,54,0,204,392],
					[0,161,0,0,0,0,0,0,204,0,148],
					[0,0,0,0,0,0,0,0,392,148,0]
				],
				
				stack:[],
				v:[],
				top : 0,
				//st : 1,
				//ed : 2,
				n : 10 ,//这里10个顶点写死，后续可以改
				
				//途径多个顶点的最佳路径
				res: [[],[],[],[],[],[],[],[],[],[],[],[],[],[],[],[],[],[],[],[],[],[],[],[],[],[],[],[],[],[],[],[],[],[],[],[],[],[]],
				j : 0,
				min : 0,
				num : 3, //途径的顶点个数（包括起点和终点）
				
				manySpotPath : [],
				
				ShortestPath : [],
				Shortestlength : 0,
				
				//求图的关节点
				Matrix : [
					[0,0,1,0,0,0,0,1,1,0],
					[0,0,1,0,0,0,0,0,0,0],
					[1,1,0,1,0,1,0,0,0,0],
					[0,0,1,0,1,1,0,0,0,0],
					[0,0,0,1,0,1,0,0,0,0],
					[0,0,1,1,1,0,1,1,0,0],
					[0,0,0,0,0,1,0,1,0,0],
					[1,0,0,0,0,1,1,0,1,1],
					[1,0,0,0,0,0,0,1,0,1],
					[0,0,0,0,0,0,0,1,1,0]
				],
				count : 0,//当前有多少个顶点已经访问过
				visited:[0,0,0,0,0,0,0,0,0,0],//用来记录顶点访问的次序
				low:[0,0,0,0,0,0,0,0,0,0],
				vertex_num : 8,
				
				//关节点
				jpoint : -1
			}
		},
		onLoad:function(options){
			this.start = JSON.parse(options.data)
			this.end = JSON.parse(options.news)
		},
		onReady() {
			//求所有路径
			this.getAllPath(this.start.id);
			//求途径多个顶点的最佳路径
			this.getManySpotPath();
			//求最短路径
			this.getShortestPath();
			//求图的关节点
			this.atriculation_point_step1(0);
		},
		methods:{
				//求所有路径
				getAllPath(pos){
					let i;
					if(pos == this.end.id){//到达终点
						for(i=0;i<this.top;i++)
							this.res[this.j][i] = this.stack[i];
						this.res[this.j][i] = this.end.id;
						this.j++;
						return;
					}
					this.v[pos] = 1;//标记被访问过
					this.stack[this.top++]=pos;//经过的路径加入队列
					for(i=1;i<=this.n;i++){ 
						if(!this.v[i] && this.map[pos][i])//如果这个点没有被访问过，而且b与这个点相连，就继续搜索
							{
								this.getAllPath(i);
							}
					}
					this.v[pos]=0;//删除标记 
					this.top--;//队列里删除b
				},
				
				//求途经这多个景点的最佳路径
				/*需求：输入起始景点，输入终止景点，再输入需途径景点的个数（包括起始景点和终止景点）
					想法是对上面求任意两个景点之间的所有路径进行筛选（筛选出途径n个景点的路径）
					然后设置一个最小值min比较找出最短的那一条
				*/
				getManySpotPath(){
					let min = 666666666666666;//初始化为一个较大的数
					let len = 0;
					let ans;
					for(let a = 0; a < this.res.length; a++)//两层for循环遍历储存在二维数组中的所有路径res
					{
						if(this.res[a].length == this.num)//筛选出经过num个顶点的路径
						{
							for(let b = 0; b < this.res[a].length; b++)
							{
									if(this.res[a][b] != this.end.id)
									{
										len += this.map[ this.res[a][b] ][ this.res[a][b+1] ];//得到经过num个顶点的路径长度
									}
							}
							if(len < min && len != 0)//得到所有经过num个顶点的路径长度的最小值
							{
								min = len;
								ans = a;
							}
							len = 0;
						}
					}
					
					if(min != 666666666666666){
						console.log("途径"+ this.num +"个顶点的最短路径长度：" + min);
						this.min = min;
						console.log("途径"+ this.num +"个顶点的最短路径：");
						this.manySpotPath = this.res[ans];
						for(let i = 0; i < this.res[ans].length; i++)
							console.log(this.res[ans][i]);
					}
					
				},
				
				//求最短路径
				getShortestPath(){
					let min = 666666666666666;//初始化为一个较大的数
					let len = 0;
					let ans;
					for(let a = 0; a < this.res.length; a++)//两层for循环遍历储存在二维数组中的所有路径res
					{
							for(let b = 0; b < this.res[a].length; b++)
							{
									if(this.res[a][b] != this.end.id)
									{
										len += this.map[ this.res[a][b] ][ this.res[a][b+1] ];//得到经过num个顶点的路径长度
									}
							}
							if(len < min && len !=0 )//得到所有经过num个顶点的路径长度的最小值
							{
								min = len;
								ans = a;
							}
							len = 0;
					}
					
					if(min != 666666666666666){
						console.log("最短路径长度：" + min);
						this.Shortestlength = min;
						console.log("最短路径：");
						this.ShortestPath = this.res[ans];
						for(let i = 0; i < this.res[ans].length; i++)
							console.log(this.res[ans][i]);
					}
					
				},
				
				//求图的关节点
				next_adjacent_vertex (v,index) {
					let i;
					for (i = index;i < 10;i++) {
						if (1 == this.Matrix[v][i]) {
							return i;
						}
					} 
					return -1;//表示没有下一个邻接点了
				},
				
				atriculation_point_step2 (v) {
						let min;
						let w = -1;
						this.visited[v] = ++this.count;
						min = this.visited[v];
						while (-1 != (w = this.next_adjacent_vertex(v,w+1))) {
							if (0 == this.visited[w]) {
								this.atriculation_point_step2 (w);
								if (this.low[w] >= this.visited[v]) {
									//console.log("-->" + v);//a的ASCII码是97
									this.jpoint = v + 1;
								}
								if (min > this.low[w]) {
									min = this.low[w];
								}
							}else if(this.visited[w] < min){
								min = this.visited[w];//w已经被访问过，w是v在生成树上的祖先
							}
						}
						this.low[v] = min;
				},
				
				atriculation_point_step1(v){
					let adjacent = this.next_adjacent_vertex (v,0);	
					this.visited[v] = ++this.count;
					this.atriculation_point_step2(adjacent);
					if (this.count < this.vertex_num) {
						console.log("-->"+ v);//a的ASCII码是97
						while (-1!= (adjacent = this.next_adjacent_vertex(v,adjacent+1))) {
							if (0 == this.visited[adjacent]) {
							    this.atriculation_point_step2(adjacent);
							}
						
						}
					}
				}
			
		}
}
</script>

<style>
	.banner {
		height: 360rpx;
		overflow: hidden;
		position: relative;
		background-color: #ccc;
	}
	
	.banner-img {
		width: 100%;
	}
	
	.banner-title {
		max-height: 84rpx;
		overflow: hidden;
		position: absolute;
		left: 30rpx;
		bottom: 30rpx;
		width: 90%;
		font-size: 32rpx;
		font-weight: 400;
		line-height: 42rpx;
		color: white;
		z-index: 11;
	}
	
	.article-meta {
		padding: 20rpx 40rpx;
		display: flex;
		flex-direction: row;
		justify-content: flex-start;
		color: gray;
	}
	
	.article-text {
		font-size: 26rpx;
		line-height: 50rpx;
		margin: 0 20rpx;
	}
	
	.article-author,
	.article-time {
		font-size: 30rpx;
	}
	
	.article-content {
		padding: 0 30rpx;
		overflow: hidden;
		font-size: 30rpx;
		margin-bottom: 30rpx;
		//display: flex;
	}
	
	.shortest-path{
		//display: flex;
	}
	
	.all-path{
		//display: flex;
	}
	
	.many-path{
		//display: flex;
	}
	.manySpotPath{
		display: flex;
	}
	.manySpotPath-item{
		//display: flex;
	}
	
	.allPath1{
		display: flex;
	}
	
	.ShortestPath{
		display: flex;
	}
	
	.line{
		border-bottom: 1rpx solid #999999;
	}
	.jpoint{
		display: flex;
	}
</style>
