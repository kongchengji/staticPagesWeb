<!--  -->
<template>
  <div class="client_section layout_padding">
    <h2 class>团队成员</h2>
    <div class="container">
      <div id="carouselExampleIndicators" class="carousel slide" data-ride="carousel">
        <ol class="carousel-indicators">
          <li data-target="#carouselExampleIndicators" data-slide-to="0" class="active"></li>
          <li
            data-target="#carouselExampleIndicators"
            :data-slide-to="i.id"
            v-for="i in tmember"
            :key="i.id"
          ></li>
        </ol>
        <div class="carousel-inner">
          <div class="carousel-item active">
            <div class="row">
              <div class="col-md-3">
                <div class="client_img-box">
                  <img src="img/teammembers/per1.jpeg" alt />
                </div>
              </div>
              <div class="col-md-9">
                <div class="client_detail-box">
                  <h5>王振超</h5>
                  <p>我是王振超，我来自昆明理工大学，平常喜欢学习一些新的技术，也会在csdn上发表一些博客展示学习的成果</p>
                </div>
              </div>
            </div>
          </div>
          <div class="carousel-item" v-for="item in tmember" :key="item.id">
            <div class="row">
              <div class="col-md-3">
                <div class="client_img-box">
                  <img :src="item.imgurl" alt />
                </div>
              </div>
              <div class="col-md-9">
                <div class="client_detail-box">
                  <h5>{{ item.name }}</h5>
                  <p>{{ item.cons }}</p>
                </div>
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
      tmember: [
        {
          id: 1,
          imgurl: "img/teammembers/per2.jpg",
          name: "司徒炜豪",
          cons: "这是司徒炜豪，平时喜欢看书，善于学习，活泼开朗"
        },
        {
          id: 2,
          imgurl: "img/teammembers/per3.jpg",
          name: "康彦丰",
          cons:
            "这是康彦丰，喜欢编程，平时作为一个路过的程序员经常帮助别人，自昆明理工大学而来"
        },
        {
          id: 3,
          imgurl: "img/teammembers/per4.jpg",
          name: "杨志芳",
          cons: "这是杨志芳，昆明理工大学的学生，动手能力很强"
        },
        {
          id: 4,
          imgurl: "img/teammembers/per5.jpg",
          name: "王煦童",
          cons: "这是王煦童，来自昆明理工大学信自学院，爱好很多，善于思考"
        },
        {
          id: 5,
          imgurl: "img/teammembers/per6.jpg",
          name: "李非",
          cons:
            "这是李非，来自昆明理工大学计算机系学习3年半的本科学生，擅长打蓝球、会唱跳rap"
        },
        {
          id: 6,
          imgurl: "img/teammembers/client.png",
          name: "吕创",
          cons:
            "这是吕创，来自昆明理工大学，平时喜欢刷刷抖音，打打英雄联盟，职业素养强"
        }
      ]
    };
  },
  created: function() {
    this.gettmembers();
  },
  //方法集合
  methods: {
    gettmembers() {
      //  this.$axios.get('http://localhost:8080/ServerJava/TmemberServlet',{
      //      params: {
      //           name: 'teammember',
      //       }
      //  }).then((response) => {
      //     //  console.log(response.data);
      //       this.tmember = response.data.teammember;
      //  })
    }
  }
};
</script>

<style>
/* client section */
.client_section h2,
.client_section h5,
.client_section p {
  font-weight: 600;
}

.client_section h2 {
  text-align: center;
}

.client_section h5 {
  font-size: 24px;
  color: #fdd31d;
}

.client_section .row {
  align-items: center;
  padding: 75px 0;
  margin: 0 15px;
}

.client_section img {
  width: 100%;
}
.client_img-box img {
  border-radius: 50%;
}
.client_img-box::before,
.client_img-box::after {
  content: "";
  position: absolute;
  width: 100px;
  height: 30px;
  border-radius: 20px;
  background-color: #fdd31d;
}

.client_img-box::before {
  top: -15px;
  transform: rotate(139deg);
  left: -15px;
  animation: beforeanimate 1s;
  animation-delay: 0.1s;
}

.client_img-box::after {
  bottom: -15px;
  transform: rotate(142deg);
  right: -15px;
  animation: afteranimate 1s;
  animation-delay: 0.1s;
}

@keyframes beforeanimate {
  0% {
    top: 43%;
    transform: rotate(142deg);
    left: 31%;
  }

  100% {
    top: -15px;
    transform: rotate(139deg);
    left: -15px;
  }
}

@keyframes afteranimate {
  0% {
    bottom: 46%;
    transform: rotate(142deg);
    right: 35%;
  }

  100% {
    bottom: -15px;
    transform: rotate(142deg);
    right: -15px;
  }
}

.client_section .carousel-indicators {
  margin: 0;
  justify-content: flex-end;
  padding-right: 15px;
  bottom: 20px;
}

.client_section .carousel-indicators li {
  width: 25px;
  height: 25px;
  background-color: #6bd1bd;
  border-radius: 100%;
  opacity: 1;
}

.client_section .carousel-indicators li.active {
  background-color: #fdd31d;
}
</style>