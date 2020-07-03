<!-- 主页面getMore的内容 -->
<template>
  <div class="getMore">
    <div class="carsgetmore" v-for="item in getmorelist" :key="item.id">
      <div class="container" v-if="(item.id%2) != 0">
        <div class="row">
          <div class="col-md-6">
            <div class="about_detail-box">
              <h3>{{item.name}}</h3>
              <p>{{item.pcon}}</p>
              <div>
                <router-link :to="item.routerlink">
                  <button>更多</button>
                </router-link>
              </div>
            </div>
          </div>
          <div class="col-md-6">
            <div>
              <img :src="item.imgurl" />
            </div>
          </div>
        </div>
      </div>
      <div class="container" v-else>
        <div class="row">
          <div class="col-md-6">
            <div>
              <img :src="item.imgurl" />
            </div>
          </div>
          <div class="col-md-6">
            <div class="about_detail-box">
              <h3>{{item.name}}</h3>
              <p>{{item.pcon}}</p>
              <div>
                <router-link :to="item.routerlink">
                  <button>更多</button>
                </router-link>
              </div>
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
      getmorelist: [
        {
          id: 1,
          name: "交通发展现状",
          pcon:
            "交通系统消耗了全球约1／3的能源。以石油产品为燃料的汽车是最主要的现代交通运输工具，它给人们带来方便和快捷的同时，也带来了无法回避的环境问题。60％以上的碳氢化合物和30％以上的氮氧化物来自汽车排放。这些污浊的气体使人类的生存环境受到极大威胁。汽车污染已成为世界性公害，其对于温室气体浓度增加的“贡献”不容忽视。",
          imgurl: "img/carsgetmore/lei1.jpg",
          routerlink: "/home/aitraffic"
        },
        {
          id: 2,
          name: "城市汽车保有量",
          pcon:
            "据公安部交通管理局统计数据，截止2018上半年全国汽车保有量达3.19亿辆，昆明也是汽车保有量超过百万的58座城市之一，昆明市交通压力巨大，寻求解决交通压力的方法迫在眉睫。如今国内实施的一些方法如尾号限行、采用轻车高架解决小车出行等。",
          imgurl: "img/carsgetmore/lei2.jpg",
          routerlink: "/home/cityrnums"
        },
        {
          id: 3,
          name: "汽车怠速消耗",
          pcon:
            "通过对汽车排量的调查，得出不同汽车的排量情况，选取1.8的排量来计算，最高怠速油耗为0.306ml/s，昆明市保有车辆259万辆，为计算方便以三分之一左右约100万辆来计算，如果每辆车一次减少等待10秒，可节约最高汽油量3060L，按市场价格汽油7元/升计算，可节省人民币21402元。",
          imgurl: "img/carsgetmore/lei3.jpg",
          routerlink: "/home/pollution"
        },
        {
          id: 4,
          name: "为什么需要智能交通灯",
          pcon:
            "近年来随着城市车辆的数量越来越多，以前的固定时间控制交通灯变化系统已经不太适用于当前的城市系统。随着技术的发展，智能化交通灯控制系统的呼声与可行性也越来越高了。",
          imgurl: "img/carsgetmore/lei1.jpg",
          routerlink: "/home/whyneed"
        }
      ]
    };
  },
  created: function() {
    this.getmorelists();
  },
  //方法集合
  methods: {
    //    getmorelists(){
    //        this.$axios.get('http://localhost:8080/ServerJava/indexMainServlet',{
    //            params: {
    //                 name: 'indexmain',
    //             }
    //        }).then((response) => {
    //         //    console.log(response.data);
    //             this.getmorelist = response.data.getmorelist;
    //        })
    //    }
  }
};
</script>

<style>
.carsgetmore {
  padding: 50px 0;
  text-align: left;
}
.carsgetmore img {
  max-width: 100%;
}
.carsgetmore:nth-child(2n) .about_detail-box button {
  background-color: #fdd31d;
  color: #fefeff;
  padding: 15px 45px;
  border-radius: 10px;
  font-size: 15px;
  transition: all 0.3s ease 0s;
}
.carsgetmore:nth-child(2n-1) .about_detail-box button {
  background-color: #6ebca8;
  color: #fefeff;
  padding: 15px 45px;
  border-radius: 10px;
  font-size: 15px;
  transition: all 0.3s ease 0s;
}
.carsgetmore .about_detail-box button:hover {
  -webkit-box-shadow: 0px 5px 10px -5px rgba(0, 0, 0, 0.7);
  -moz-box-shadow: 0px 5px 10px -5px rgba(0, 0, 0, 0.7);
  box-shadow: 0px 5px 10px -5px rgba(0, 0, 0, 0.7);
  transform: translateY(-7px);
}
</style>