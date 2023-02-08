# Multi-Objective-Recommender-System
### 基于亿万用户会话事件及冷启动问题, 预测点击、购物车添加和订单商品
## Retrieval
## 生成候选
### Co-visitation Matrixes
#### click/cart/order to cart/order,cart/order to cart/order, click/cart/order to clicks
### weights
#### type weight:df['wgt'] = df.type_y.map(type_weight), type_weight = {0:1, 1:6, 2:3} 
#### distance weight:df['wgd'] = (1/2)**( (df.d_x - df.d_y).abs()),df['d'] = np.arange(len(df))  
#### timestamp weight:df['wgts'] = (1/2)**( (df.ts_x - df.ts_y).abs() /60/60)
### 用户历史 clicks, carts, orders 
###  当前最受欢迎的 Top20 clicks, carts, orders
## Rerank
### Features
#### 用户：聚合统计
#### 商品：聚合统计
#### 用户-商品：itemCF 分数
### Ranking Model
#### XGBoost
