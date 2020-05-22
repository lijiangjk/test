<template>
<div class="pos">
  <el-row>
    <el-col :span="7" class="diai" id="odis">
      <el-tabs>
        <el-tab-pane label="订单">
          <el-table :data="taidte" border style="width: 100%;">
            <el-table-column prop="godname" label="商品名称"></el-table-column>
            <el-table-column prop="count" label="量" width="50"></el-table-column>
            <el-table-column prop="price" label="金额" width="70"></el-table-column>
            <el-table-column  label="操作" width="100" fixed="right">
              <template scope="scope">
                <el-button type="text" size="small">删除</el-button>
                <el-button type="text" size="small">增加</el-button>
              </template>
            </el-table-column>
          </el-table>
          <div class="div-dit">
            <el-button type="warning">挂单</el-button>
            <el-button type="danger">删除</el-button>
            <el-button type="success">结账</el-button>
          </div>
        </el-tab-pane>
        <el-tab-pane label="商店">

        </el-tab-pane>
        <el-tab-pane label="外卖">

        </el-tab-pane>
      </el-tabs>

    </el-col>

    <el-col :span="17">
      <div class="main-lit">
        <div class="mian-lat">常用商品</div>
        <div class="main-pit">
          <ul>
            <li v-for="item in ofte">
              <span>{{item.gtname}}</span>
              <span class="main-yis">￥{{item.price}}元</span>
            </li>
          </ul>
        </div>
      </div>
      <div class="miat">
        <el-tabs>
          <el-tab-pane label="汉堡">
            <div>
              <ul class='cookList'>
                  <li v-for="item in pitn">
                      <span class="foodImg"><img :src="item.goodsImg" width="100%"></span>
                      <span class="foodName">{{item.goodsName}}</span>
                      <span class="foodPrice">￥{{item.price}}元</span>
                  </li>
              </ul>
            </div>
          </el-tab-pane>
          <el-tab-pane label="小吃">
           小吃
          </el-tab-pane>
          <el-tab-pane label="饮料">
            饮料
          </el-tab-pane>
          <el-tab-pane label="套餐">
            套餐
          </el-tab-pane>
        </el-tabs>
      </div>
    </el-col>
  </el-row>
</div>
</template>

<script>
export default {
  name: 'pos',
  data(){
    return{
      taidte:[{
        godname:'可口可乐',
        price:8,
        count:1
      },{
        godname:'香辣鸡腿堡',
        price:15,
        count:1
      },{
        godname:'爱心薯条',
        price:8,
        count:1
      },{
        godname:'甜筒',
        price:8,
        count:1
      }],
      ofte:[
        {
          gtid:1,
          gtname:'香辣鸡腿堡',
          price:18
        },
        {
          gtid:2,
          gtname:'可口可乐',
          price:8
        },
        {
          gtid:3,
          gtname:'香辣鸡腿',
          price:12
        },
        {
          gtid:4,
          gtname:'可乐鸡翅',
          price:20
        },
        {
          gtid:5,
          gtname:'油闷大虾',
          price:23
        },
        {
          gtid:6,
          gtname:'爆米花',
          price:13
        }
      ],
      pitn:[
         {
              goodsId:1,
              goodsImg:"http://7xjyw1.com1.z0.glb.clouddn.com/pos001.jpg",
              goodsName:'香辣鸡腿堡',
              price:18
          }, {
              goodsId:2,
              goodsImg:"http://7xjyw1.com1.z0.glb.clouddn.com/pos002.jpg",
              goodsName:'田园鸡腿堡',
              price:15
          }, {
              goodsId:3,
              goodsImg:"http://7xjyw1.com1.z0.glb.clouddn.com/pos004.jpg",
              goodsName:'和风汉堡',
              price:15
          }, {
              goodsId:4,
               goodsImg:"http://7xjyw1.com1.z0.glb.clouddn.com/pos003.jpg",
              goodsName:'快乐全家桶',
              price:80
          }, {
              goodsId:5,
               goodsImg:"http://7xjyw1.com1.z0.glb.clouddn.com/pos003.jpg",
              goodsName:'脆皮炸鸡腿',
              price:10
          }, {
              goodsId:6,
               goodsImg:"http://7xjyw1.com1.z0.glb.clouddn.com/pos004.jpg",
              goodsName:'魔法鸡块',
              price:20
          }, {
              goodsId:7,
               goodsImg:"http://7xjyw1.com1.z0.glb.clouddn.com/pos001.jpg",
              goodsName:'可乐大杯',
              price:10
          }, {
              goodsId:8,
               goodsImg:"http://7xjyw1.com1.z0.glb.clouddn.com/pos003.jpg",
              goodsName:'雪顶咖啡',
              price:18
          }, {
              goodsId:9,
               goodsImg:"http://7xjyw1.com1.z0.glb.clouddn.com/pos002.jpg",
              goodsName:'大块鸡米花',
              price:15
          }, {
              goodsId:20,
               goodsImg:"http://7xjyw1.com1.z0.glb.clouddn.com/pos002.jpg",
              goodsName:'香脆鸡柳',
              price:17
          }
      ]
    }
  },
  mounted:function(){
    var odeis=document.body.clientHeight;
    document.getElementById('odis').style.height=odeis+'px';
  }
}
</script>

<style>
.diai{
  background-color:#f9fafc;
  border-right:1px solid #C0CCDA;
}
.el-tabs__item{
  padding: 0px 20px !important;
}
.el-tabs__header{
  margin: 0px !important;
}
.div-dit{
  margin-top: 10px;
}
.main-pit ul li{
  list-style: none;
  float: left;
  border: 1px solid #e5e9f2;
  padding: 10px;
  margin: 10px;
  background-color: #FFFFFF;
}
.mian-lat{
  height: 20px;
  border-bottom:1px solid #D3DCE6;
  background-color: #F9FAFC;
  padding: 10px;
  text-align: left;
}
.main-yis{
  color: #58b7ff;
}
.miat{
  clear: both;
}
.cookList li{
       list-style: none;
       width:23%;
       border:1px solid #E5E9F2;
       height: auot;
       overflow: hidden;
       background-color:#fff;
       padding: 2px;
       float:left;
       margin: 2px;

   }
   .cookList li span{

        display: block;
        float:left;
   }
   .foodImg{
       width: 40%;
   }
   .foodName{
       font-size: 18px;
       padding-left: 10px;
       color:brown;

   }
   .foodPrice{
       font-size: 16px;
       padding-left: 10px;
       padding-top:10px;
   }
</style>
