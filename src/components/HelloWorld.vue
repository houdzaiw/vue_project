<template>
<div  class="layout" :style="bgImg">
<div>
   <Layout style="height:790px;border-radius: 20px;">
        <Layout style="background:#FEFEFE;borderBottomLeftRadius:20px;borderTopLeftRadius:20px">
        <!--头部logo 导航 搜索 -->
            <Header class="header" style="background:#FEFEFE">
             <Row>
                <Col span="4"> <img src="../assets/logo.png" /></Col>
                <!-- 导航 -->
                <Col span="14">
                     <div style="margin-top:15px">
             <Menu mode="horizontal" :theme="theme1" active-name="1">
              <MenuItem name="1">
                  Dashboard
              </MenuItem>
              <MenuItem name="2">
                  Services
              </MenuItem>
              <MenuItem name="3">
                  History
              </MenuItem>
              <MenuItem name="4">
                  Actions
              </MenuItem>
            </Menu>
            </div>
                </Col>
                <!-- 搜索 -->
                <Col span="6"
                     <div style="margin-top:15px">
               <Input placeholder="search" style="width: auto">
            <Icon type="ios-search" slot="suffix" />
        </Input>
            </div>
                </Col>
            </Row>
            </Header>
            <Content>
            <!--cards 部分 -->
               <div>
                    <div class="content-card">
                        <div style="font-size:18px">Cards</div>
                        <div>VIew all Cards</div>
                    </div>
                    <Row style="margin-top:20px">
                        <Col span="8">
                            <div style="margin-left:130px">
                         <img class="card-img" src="../assets/cards5.png" />
                       </div>
                        </Col>
                        <Col span="8">
                            <div style="margin-left:80px">
                         <img class="card-img" src="../assets/card6.png" />
                       </div>
                        </Col>
                        <Col span="8">
                            <Card class="card-Upload">
                            <div class="card-Upload-content">
                             <Upload action="//jsonplaceholder.typicode.com/posts/">
                                 <Icon style="font-size:30px" type="ios-add-circle-outline" />
                            </Upload>
                                <h3>Add New Card</h3>
                            </div>
                        </Card>
                        </Col>
                    </Row>
                    
               </div>

                <!--Main Services 模块-->
               <div class="main-content">
                <!--Main Services 左边模块-->
                    <div class="main-content-left">
                       <div class="content-bottom-left">
                        <h3>Main Services</h3>
                        <div>View all</div>
                       </div>
                       <div class="card-exhibition">
                             <Card class="main-tr-card" >
                            <div style="text-align:center;">
                            <Icon class="main-tr-card-img" type="ios-swap" />
                                <h6>Transac</h6>
                            </div>
                        </Card>

                         <Card class="main-Utility-card">
                            <div style="text-align:center;">
                            <Icon class="main-tr-card-img"  type="md-bulb" />
                                <h6>Utility</h6>
                            </div>
                        </Card>
                       </div>

                       <div class="card-exhibition" style="display:flex;margin-top:20px">
                             <Card class="main-tr-card">
                            <div style="text-align:center;">
                            <img class="main-Utility-card-img" src="../assets/qd1.png" />
                                <h6>
                                Loanhs</h6>
                            </div>
                        </Card>

                         <Card class="main-Utility-card">
                            <div style="text-align:center;">
                             <img class="main-Utility-card-img" src="../assets/jsb.png" />
                                <h6>
                                Deposits</h6>
                            </div>
                        </Card>
                       </div>

                       <div class="card-exhibition">
                             <Card class="main-tr-card">
                            <div style="text-align:center;">
                             <img class="main-Utility-card-img"  src="../assets/nz.png" />
                                <h6>Fasttranhsfer</h6>
                            </div>
                        </Card>

                         <Card class="main-Utility-card">
                            <div style="text-align:center;">
                           <img class="main-Utility-card-img" src="../assets/jt.png" />
                                <h6>
                                Exchahnge</h6>
                            </div>
                        </Card>
                       </div>
                    </div>
                      <!--Main Services 右边模块-->
                    <div class="main-current">
                        <div>
                            <div class="main-current-text">
                                <h3>Current</h3>
                                <div>VIew All</div>
                            </div>
                            <div v-for="item in todayList" :key=index class="main-current-currentList">
                              <div  class="main-current-currentList-name"> {{item.name}}</div>
                              <div style="margin-left:20px;flex-grow:2;">- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -</div>
                              <div class="main-current-currentList-name"><h4> {{item.price}}</h4></div>
                            </div>
                        </div>
                       <div>
                            <div class="savings-content">
                                <h3>Savings</h3>
                                <div>VIew All</div>
                            </div>
                            <!--Main Services 右边统计图模块-->
                            <div style="margin-top:20px;display:flex">
                                 <div style="width:620px;margin-left:10px" id="container1"></div>
                                 <div style="display:flex;justify-content:flex-end">
                                    <div style="flex1;padding-left:40px;padding-right:150px">
                                        <div class="savings-week">Total</div>
                                        <div class="savings-week">This week</div>
                                        <div class="savings-week">This month</div>
                                    </div>
                                    <div style="text-align:right">
                                        <div class="savings-week"><h4>$100.09</h4></div>
                                        <div class="savings-week"><h4>$2567.89</h4></div>
                                        <div class="savings-week"><h4>$123.09</h4></div>
                                    </div>
                                 </div>
                            </div>
                        </div>
                    </div>
               </div>
            </Content>
        </Layout>
         <Sider class="sider-content" hide-trigger style="width: 300px; min-width:300px; max-width: 300px; flex: 0 0 200px;">
            <div class="sider-top">
                <Icon style="font-size:24px" type="md-notifications-outline" />
                <div class="sider-top-right">
                    <div>Anastasia</div>
                    <Avatar class="sider-top-right-img" src="http://img0.imgtn.bdimg.com/it/u=3900277985,551209145&fm=11&gp=0.jpg"/>
                </div>
            </div>
            <div id="container">
            </div>
            <div class="sider-today">
                <div class="sider-today-text">Transactions</div>
                 <Select v-model="model3" style="width:100px">
                    <Option v-for="item in cityList" :value="item.value" :key="item.value">{{ item.label }}</Option>
                </Select>
            </div>
            <div class="sider-statistics" v-for="item in currentList" :key=index>
                 <img style="width:25px;height:25px;margin-right:10px" src="../assets/q2.png" />
                <div class="sider-statistics-text">{{item.name}}</div>
                <div class="sider-statistics-price">{{item.price}}</div>
            </div>
            
            <div class="sider-Button-content">
                 <Button class="sider-Button" type="error">
                    <span>Transfer Money</span>
                    <Icon style="font-size:18px;margin-left:50px" type="md-arrow-forward" />
                 </Button>
            </div>
            <div>
                 <img style="width:80px;height:75px;margin-right:10px;margin-left:190px;margin-top:70px" src="../assets/xx.png" />
            </div>
         </Sider>
    </Layout>
</div>
</div>
</template>


<script>
import ChartView from "./ChartView";
import { Chart, registerShape } from '@antv/g2';
    export default {
        name: 'HellowWorld',
    components: {
        ChartView,
    },
    data(){
        return{
            bgImg:{
                backgroundImage: "url(" + require("../assets/bg1.png") + ")",
　　　　　　　　　backgroundRepeat: "no-repeat",
                backgroundSize:'100% 100%'
            },
            currentList: [
                    {
                        name: 'Dribbble pro Plan',
                        price: '-$100'
                    },
                    {
                         name: 'Adidas Refund',
                        price: '+$230'
                    },
                    {
                         name: 'Wacom LCD',
                        price: '-$3000'
                    },
                ],

                 todayList: [
                    {
                        name: '1063873637834',
                        price: ' $2,200.01'
                    },
                    {
                         name: '1063873637834',
                        price: '$1,300.89'
                    },
                    {
                         name: '1063873637834',
                        price: '$1,848.11'
                    },
                ],
            cityList: [
                    {
                        value: 'New York',
                        label: 'New York'
                    },
                    {
                        value: 'London',
                        label: 'London'
                    },
                    {
                        value: 'Sydney',
                        label: 'Sydney'
                    },
                    {
                        value: 'Ottawa',
                        label: 'Ottawa'
                    },
                    {
                        value: 'Paris',
                        label: 'Paris'
                    },
                    {
                        value: 'Canberra',
                        label: 'Canberra'
                    }
                ],
                model2: '',
                model3: '',
                model4: ''
        }
    },

      mounted: function() {
    this.$nextTick(() => {
      this.Creatediagram();
      this.Createlinechart();
    });
  },

  methods: {

      Creatediagram(){
     const data = [
  { type: '分类一', value: 20 },
  { type: '分类二', value: 18 },
  { type: '分类三', value: 32 },
  { type: '分类四', value: 15 },
  { type: 'Other', value: 15 },
];

// 可以通过调整这个数值控制分割空白处的间距，0-1 之间的数值
const sliceNumber = 0.01;

// 自定义 other 的图形，增加两条线
registerShape('interval', 'slice-shape', {
  draw(cfg, container) {
    const points = cfg.points;
    let path = [];
    path.push(['M', points[0].x, points[0].y]);
    path.push(['L', points[1].x, points[1].y - sliceNumber]);
    path.push(['L', points[2].x, points[2].y - sliceNumber]);
    path.push(['L', points[3].x, points[3].y]);
    path.push('Z');
    path = this.parsePath(path);
    return container.addShape('path', {
      attrs: {
        fill: cfg.color,
        path,
      },
    });
  },
});

const chart = new Chart({
  container: 'container',
  autoFit: true,
  height:290,
});

chart.data(data);
chart.coordinate('theta', {
  radius: 0.75,
  innerRadius: 0.6,
});
chart.tooltip({
  showTitle: false,
  showMarkers: false,
});
chart
  .interval()
  .adjust('stack')
  .position('value')
  .color('type')
  .shape('slice-shape');

chart.render();
      },

      Createlinechart(){
          const data = [
  { year: '$10', value: 3 },
  { year: '$20', value: 4 },
  { year: '$30', value: 3.5 },
  { year: '$40', value: 5 },
  { year: '$50', value: 4.9 },
  { year: '$60', value: 6 },
  { year: '$70', value: 7 },
  { year: '$80', value: 9 },
  { year: '$90', value: 13 },
];
const chart = new Chart({
  container: 'container1',
  autoFit: true,
  height: 10,
});

chart.data(data);
chart.scale({
  year: {
    range: [0, 1],
  },
  value: {
    min: 0,
    nice: true,
  },
});

chart.tooltip({
  showCrosshairs: true, // 展示 Tooltip 辅助线
  shared: true,
});

chart.line().position('year*value').label('value');
chart.point().position('year*value');

chart.render();
      }
  }
    }

    
</script>
<style>

.layout{
    height: 890px;
     width: 100%;
     padding:50px;
}
.content-card{
    display:flex;
    justify-content:space-between;
    padding-top:50px;
    padding-left:130px;
    padding-right:130px;
}
.card-exhibition{
    display:flex;
    margin-top:20px
}
.card-img{
    width:336px;
    height:193px;
    border-radius:20px
}
.savings-week{
    margin-bottom:8px;
}
.main-current-currentList-name{
    margin-left:20px;
    flex-grow:1
}
.main-content-left{
    height:350px;
    width:290px;
}
.main-current{
    width:auto;
    margin-left:60px
}
.sider-Button{
    margin-left:50px;
    width:200px;
    height:45px;
    border-radius:40px;
    background:#FF4D56
}
.main-tr-card-img{
    font-size:30px;
    color:#FF656D
}
.savings-content{
    display:flex;
    justify-content:space-between;
    margin-left:20px;
    margin-top:20px
}
.card-Upload{
    width:336px;
    height:193px;
    margin-left:60px;
    background:#F8F8F8
}
.main-current-currentList{
    margin-top:20px;
    display:flex
}
.main-tr-card{
    width:85px;
    height:85px;
    background:#fff;
    margin-left:10px;
    margin-right:50px;
    border-radius:20px
}
.main-current-text{
    display:flex;
    justify-content:space-between;
    margin-left:20px
}
.main-Utility-card-img{
    width:30px;
    height:30px
}
.main-Utility-card{
    width:85px;
    height:85px;
    background:#fff;
    margin-left:10px;
    border-radius:20px
}
.main-content{
    display:flex;
    margin-left:130px;
    margin-top:20px;
    flex:1;
}
.card-Upload-content{
        text-align:center;
        margin-top:40px
    }

.content-bottom-left{
    display:flex;
    justify-content:space-between;
}

.sider-top{
    display:flex;
    padding:15px;
    justify-content:space-between;
}
.sider-top-right{
    display:flex;
}
.sider-top-right-img{
    margin-left:8px;
    border-radius: 50px;
    width:30px;
    height:30px;
    margin-top:-5px
}
.sider-today{
    display:flex;
    justify-content:space-between;
    padding:10px;
}
.sider-today-text{
    margin-top:5px
}
.sider-statistics{
    display:flex;
    margin-top:20px;
}

.sider-statistics-img{
    flex:1;
    width:20px;
    height:20px;
}
.sider-statistics-text{
    flex:4
}
.sider-statistics-price{
    flex:1;
}
.sider-Button-content{
    margin-top:30px;
}
.ivu-layout-header {
    background: #fff;
    padding: 0 50px;
    height: 64px;
    line-height: 64px;
}


.ivu-layout-sider {
    -webkit-transition: all .2s ease-in-out;
    transition: all .2s ease-in-out;
    position: relative;
    background: #fff;
    border-radius: 20px;
    min-width: 0;
}
.ivu-layout-sider-trigger {
    position: fixed;
    bottom: 0;
    text-align: center;
    cursor: pointer;
    height: 48px;
    line-height: 48px;
    color: #fff;
    background: #fff;
    z-index: 1000;
    transition: all .2s ease-in-out;
}

.ivu-select-selection {
    display: block;
    /* box-sizing: border-box; */
    outline: 0;
    -webkit-user-select: none;
    -ms-user-select: none;
    user-select: none;
    cursor: pointer;
    position: relative;
    /* background-color: #fff; */
    /* border-radius: 4px; */
     border: 1px solid #fff; 
    transition: all .2s ease-in-out;
}

.ivu-menu-light {
     background: #FEFEFE
; 
}

.ivu-menu-light.ivu-menu-horizontal .ivu-menu-item, .ivu-menu-light.ivu-menu-horizontal .ivu-menu-submenu {
    height: inherit;
    line-height: inherit;
    border-bottom: 2px solid transparent;
    color: #8a8a8a;
}

.ivu-menu-light.ivu-menu-horizontal .ivu-menu-item-active, .ivu-menu-light.ivu-menu-horizontal .ivu-menu-item:hover, .ivu-menu-light.ivu-menu-horizontal .ivu-menu-submenu-active, .ivu-menu-light.ivu-menu-horizontal .ivu-menu-submenu:hover {
    color: #2c2c2c;
}
.ivu-menu-light.ivu-menu-horizontal .ivu-menu-item-active, .ivu-menu-light.ivu-menu-horizontal .ivu-menu-item:hover, .ivu-menu-light.ivu-menu-horizontal .ivu-menu-submenu-active, .ivu-menu-light.ivu-menu-horizontal .ivu-menu-submenu:hover {
    color: #2c2c2c;
/*border-bottom: 2px solid #2d8cf0;*/
}

.ivu-input {
    display: inline-block;
    width: 100%;
    height: 32px;
    line-height: 1.5;
    padding: 4px 7px;
    font-size: 14px;
    border: 1px solid #F8F8F8;
    border-radius: 20px;
    color: #515a6e;
    background-color:#F8F8F8;
    background-image: none;
    position: relative;
    cursor: text;
    transition: border .2s ease-in-out,background .2s ease-in-out,box-shadow .2s ease-in-out;
}

.ivu-select-visible .ivu-select-selection {
    border-color: #FFF;
    outline: 0;
    box-shadow: 0 0 0 1px #FFF;
}
.ivu-select-selection-focused, .ivu-select-selection:hover {
    border-color: #fff;
}

.ivu-menu-light.ivu-menu-horizontal .ivu-menu-item, .ivu-menu-light.ivu-menu-horizontal .ivu-menu-submenu {
    height: inherit;
    line-height: inherit;
    border-bottom: 2px solid #F8F8F8;
    color: #8a8a8a;
}

.ivu-menu-horizontal.ivu-menu-light:after {
    content: '';
    display: block;
    width: 100%;
    height: 1px;
    background: #dcdee2;
    position: absolute;
    bottom: 0;
    border-bottom: #F8F8F8 1px solid;
    left: 0;
}

</style>

