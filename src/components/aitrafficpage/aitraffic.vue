<!--  -->
<template>
  <div class="aitraffic">
    <div class="container">
      <div class="row">
        <div class="col-md-4">
          <h2>
            <span class="iconfont icon-jiaotong"></span>
            智能交通
          </h2>
        </div>
        <div class="col-md-8">
          <p>目前，中国交通已经随着人民汽车保有量的增加进入了一个全新的阶段，传统的路口交通控制信号灯已经无法满足当前的路口堵塞、车辆流通等问题。随着人工智能、物联网等新一代信息技术加速应用，智能化交通的概念呼之欲出。</p>
        </div>
      </div>
    </div>
    <div class="textcon" v-for="item in listaitraffic" :key="item.name">
      <div class="container" v-if="(item.id%2) != 0">
        <div class="row">
          <div class="col-md-6">
            <div class="textnei">
              <h3>{{item.name}}</h3>
              <p>{{item.con}}</p>
              <ul class="list-unstyled">
                <li v-for="(is,j) in item.exam.split('|')" :key="j">
                  <span class="iconfont icon-youshiyuquedian"></span>
                  &nbsp;&nbsp; {{is}}
                </li>
              </ul>
            </div>
          </div>
          <div class="col-md-6">
            <img :src="item.imgurl" />
          </div>
        </div>
      </div>
      <div class="container" v-else>
        <div class="row">
          <div class="col-md-6">
            <img :src="item.imgurl" />
          </div>
          <div class="col-md-6">
            <div class="textnei">
              <h3>{{item.name}}</h3>
              <p>{{item.con}}</p>
              <ul class="list-unstyled">
                <li v-for="(is,j) in item.exam.split('|')" :key="j">
                  <span class="iconfont icon-youshiyuquedian"></span>
                  &nbsp;&nbsp; {{is}}
                </li>
              </ul>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    //这里存放数据
    return {
      listaitraffic: [
        {
          id: 1,
          name: "传统交通路口",
          imgurl: "img/listaitraffic/oldlight.jpg",
          con: "传统的交通路口控制车辆的通行通常使用固定时长的红绿灯来进行控制",
          exam:
            "缺点1：不能够根据道路上的车辆情况进行实时的控制|缺点2：交通通行效率低下，有时需要大量人力监管|缺点3：不能根据当前车流量对红绿灯变化做出改变"
        },
        {
          id: 2,
          name: "智能交通路口",
          imgurl: "img/listaitraffic/ailight.jpg",
          con:
            "21世纪将是公路交通智能化的世纪，人们将要采用的智能交通控制系统，是一种先进的一体化交通综合管理系统。在该系统中，车辆靠自己的智能在道路上自由行驶，公路靠自身的智能将交通流量调整至最佳状态，借助于这个系统，管理人员对道路、车辆的行踪将掌握得一清二楚。",
          exam:
            "好处1：更加关注公众出行、交通安全等民生需求，更加适合我国国情、地域和行业特点|好处2：更需要企业和社会力量的参与，并将自主创新与集成创新结合起来|好处3：以构建安全、便捷、高效、绿色的交通运输体系为目标，充分满足公众出行和货物运输多样化需求"
        },
        {
          id: 3,
          name: "发展情况",
          imgurl: "img/listaitraffic/dev.jpg",
          con:
            "近几年，我国一部分城市例如上海、杭州等地开始在特定路口对交通灯的控制进行改进，深圳、北京、南京等地开始试行“绿波带“（即尽可能保证车辆以一定车速行驶可以一路畅通无阻）。据查阅资料和相关媒体报道，在2006年海口市龙昆南路开通的”绿波带“试行三年后，即2009年，其作用已经大打折扣，车辆难过，行人亦难过；与此同时，我们团队还在离我们最近的呈贡彩云南路的绿波带进行了实地勘察，该”绿波带“虽起到一定作用，但从结果来看，其效果与我们预期构想存在很大差异。",
          exam: "缺点1|缺点2|缺点3"
        },
        {
          id: 4,
          name: "人们评价",
          imgurl: "img/listaitraffic/ping.jpg",
          con:
            "宁波从澳大利亚重金引入了一套城市红绿灯智能控制系统，这确实是明智之举。遗憾的是，目前宁波的红绿灯感觉实在弱智，毫无智能可言。往往相邻2个路口的红绿灯会同时亮灭，也就是说，没有错时，你要通过下一个路口，时速至少在60公里以上（甚至100公里）才有希望不吃上红灯。<br>灵桥东西两个红绿灯连成什么绿色通道，其实每次开车都是过了一个却被另一个拦停了，结果每次桥上都堵车",
          exam: "-----天一论坛"
        },
        {
          id: 5,
          name: "智能城市的红绿灯",
          imgurl: "img/listaitraffic/ping.jpg",
          con:
            "最简单的，他说，世界上最遥远的距离是红绿灯和交通监控摄像头的距离。它们在一个杆子上，却从未通过数据被连接过。\r\n去年4月，王坚牵头十几家企业跟杭州市政府联合发起“城市大脑”项目，希望利用城市的数据资源，对整个城市进行全局实时分析，自动调配公共资源，最终把数据变成城市治理的最重要资源。\r\n智能技术发展到今天，让这个想法变得更加可能。\r\n今天，杭州已经有5万个交通摄像头充当“眼睛”来采集车流数据，通过人工智能方法处理后，就可以智能调控红绿灯，改善交通状况。",
          exam: "——新浪新闻《阿里王坚：真正的理想主义，都是拿命来填！》"
        }
      ]
    };
  },
  created: function() {
    this.getjavatables();
  },
  //方法集合
  methods: {
    getjavatables() {
      //     this.$axios.get('http://localhost:8080/ServerJava/aitrafficServlet',{
      //        params: {
      //             name: 'aitraffic',
      //         }
      //    }).then((response) => {
      //        console.log(response.data.Listaitraffic);
      //        this.listaitraffic = response.data.Listaitraffic;
      //    })
      //    console.log(this.listaitraffic[0].exam)
    }
  }
};
</script>

<style>
.icon-jiaotong {
  font-size: 28px;
}
.aitraffic {
  margin-top: 50px;
  padding: 50px 0;
}
.aitraffic .textcon {
  margin-top: 50px;
}
.aitraffic h2 {
  display: flex;
  justify-content: center;
  align-items: center;
}
.aitraffic .container .col-md-6 img {
  width: 100%;
}
.textnei {
  border-radius: 10px;
  height: 100%;
  padding: 10px 10px;
}
.textcon:nth-child(2n) .textnei {
  border: 1px solid #fff7e8;
  background-color: #fff7e8;
}
.textcon:nth-child(2n-1) .textnei {
  border: 1px solid #ebf9f4;
  background-color: #ebf9f4;
}
.textnei p {
  padding: 15px 0;
}
.textnei .list-unstyled {
  padding-left: 0;
  list-style: none;
}
</style>