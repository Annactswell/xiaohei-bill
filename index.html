<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>小黑记账清单</title>

  <style>
    * {
      padding: 0;
      margin: 0;
      box-sizing: border-box;
    }

    input {
      display: block;
      margin: 0.2rem 0.5rem;
      width: 9rem;
      height: 0.9rem;
      padding-left: 0.1rem;
      font-size: 0.5rem;
      outline: none;
    }

    button.add {
      width: 2rem;
      height: 1rem;
      color: white;
      background-color: rgb(108, 108, 240);
      border-radius: 0.15rem;
      margin-left: 7.5rem;
      font-size: 0.4rem;
      border: none;
    }

    a {
      text-decoration: none;
      color: blue;
      cursor: pointer;
    }

    #bill table {
      text-align: center;
      margin: 0.5rem 0.5rem;
      width: 9rem;
      font-size: 0.4rem;
    }

    #bill p {
      margin-left: 0.5rem;
      font-size: 0.5rem;
    }

    .red {
      color: red;
    }

    .echarts-box {
      margin: 0.5rem 1rem;
      width: 8rem;
      height: 8rem;
      border: 1px solid gray;
    }
  </style>
</head>
<body>
  <div id="bill">
    <div class="add">
      <input type="text" placeholder="消费名称" v-model.trim="name">
      <input type="number" placeholder="消费价格" v-model.number="price">
      <button v-on:click="add" class="add">添加账单</button>
    </div>
    <table border="1">
      <thead>
        <tr>
          <th>编号</th>
          <th>消费名称</th>
          <th>消费价格</th>
          <th>操作</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(item, index) in list" v-bind:key="item.id">
          <td>{{ index + 1 }}</td>
          <td>{{ item.name }}</td>
          <td v-bind:class="{ red: item.price >= 500 }">{{ Number(item.price).toFixed(2) }}</td>
          <td><a v-on:click="del(item.id)">删除</a></td>
        </tr>
      </tbody>
    </table>
    <p>消费总计：{{ totalPrice.toFixed(2) }}</p>
    <div class="echarts-box"></div>
  </div>
  
  <script src="axios.js"></script>
  <script src="Vue2.js"></script>
  <script src="echarts.js"></script>
  <script src="flexible.js"></script>
  <script>
    const bill = new Vue({
      el: '#bill',
      data: {
        name: '',
        price: '',
        list: []
      },
      methods: {
        getList: async function() {
          await axios({
            url: 'https://applet-base-api-t.itheima.net/bill',
            method: 'GET',
            params: {
              creator: 'Annactswell'
            }
          }).then(result => {
            this.list = result.data.data;
          });
          this.chart.setOption({
            series: [
              {
                data: this.list.map(item => ({ name: item.name, value: item.price }))
              }
            ]
          })
        },
        add: async function() {
          if (this.name.trim() === '' || this.price < 0) {
            alert('非法输入');
          } else {
            await axios({
              url: 'https://applet-base-api-t.itheima.net/bill',
              method: 'POST',
              data: {
                creator: 'Annactswell',
                name: this.name,
                price: this.price
              }
            }).then(result => {
              // console.log(result);
            });
            this.getList();
            this.name = '';
            this.price = '';
          }
        },
        del: async function(id) {
          await axios({
            url: 'https://applet-base-api-t.itheima.net/bill/' + id,
            method: 'DELETE'
          });
          this.getList();
        }
      },
      computed: {
        totalPrice: function() {
          return this.list.reduce((sum, item) => sum + Number(item.price), 0);
        }
      },
      created: function() {
        this.getList();
      },
      mounted: function() {
        this.chart = echarts.init(document.querySelector('.echarts-box'));
        let option = {
          title: {
            text: '消费列表',
            subtext: 'from Annactswell',
            left: 'center'
          },
          tooltip: {
            trigger: 'item'
          },
          legend: {
            orient: 'vertical',
            left: 'left'
          },
          series: [
            {
              name: '消费账单',
              type: 'pie',
              radius: '50%',
              data: this.list.map(item => ({ name: item.name, value: item.price })),
              emphasis: {
                itemStyle: {
                  shadowBlur: 10,
                  shadowOffsetX: 0,
                  shadowColor: 'rgba(0, 0, 0, 0.5)'
                }
              }
            }
          ]
        };
        this.chart.setOption(option);
      }
    });
  </script>
</body>
</html>
