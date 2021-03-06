# tu-an vue
**https://github.com/emmilia-hub/tuan_vue**
# TuanBS_API_Refrence
---
> Tips: python scripts are not here
---

## **baseUrl：{serverIp}:{serverPort}/TuanAPI**

---

### **API1：**

* 路由：/domain

* 概述：上传图片对图片进行处理，返回处理结果

* 方法：POST

* 参数及说明：tag、type、file

    * param：tag, type

      |       | tag=attack           | tag=defense                                                  |
      | ----- | -------------------- | ------------------------------------------------------------ |
      | type= | CW/FGSM/(其他走默认) | adv_inception_v3/ens3_adv_inception_v3/ens4_adv_inception_v3/fuzzy_integration/(其他走默认)|

    * fromData：file(img文件)

* 返回信息（JSON）：

  eg:

  ```json
  {
      "code": 1000,
      "msg": "success!",
      "record": {
          "id": "220620110614ce02b9c66ad9",
          "tag": "attack",
          "type": "attack",
          "createTime": "2022-06-20 11:06:14",
          "simg": {
              "id": "220620110614ce02b9c66ad9",
              "url": "{serverIp}:{serverPort}/profile/pics/3cf5453c71564f33813389ce93ae5b34.webp",
              "imgInfo": {
                  "racer": 7.96,
                  "convertible": 23.92,
                  "beach wagon": 5.15,
                  "amphibian": 18.16,
                  "sports car": 14.87
              }
          },
          "rimg": {
              "id": "220620110614ce02b9c66ad9",
              "url": "{serverIp}:{serverPort}/profile/pics/attack_3cf5453c71564f33813389ce93ae5b34.webp",
              "imgInfo": {
                  "racer": 10.39,
                  "car wheel": 1.29,
                  "convertible": 10.92,
                  "beach wagon": 3.01,
                  "sports car": 53.36
              }
          }
      }
  }
  ```

  ---

### **API2：**

* 路由：/domainByRid

* 概述：对已上传于服务器上的图片进行处理，返回处理结果

* 方法：POST

* 参数及说明：tag、type、id

    * param：tag、type

      |       | tag=attack           | tag=defense                                                  |
      | ----- | -------------------- | ------------------------------------------------------------ |
      | type= | CW/FGSM/(其他走默认) | adv_inception_v3/ens3_adv_inception_v3/ens4_adv_inception_v3/fuzzy_integration/(其他走默认)|



    * id：从服务器获取的img的id

* 返回信息(JSON)：

  eg:

  ```json
  {
      "code": 1000,
      "msg": "success!",
      "record": {
          "id": "22062011101085304b1850da",
          "tag": "defense",
          "type": "defense",
          "createTime": "2022-06-20 11:10:10",
          "simg": {
              "id": "22062011101085304b1850da",
              "url": "{serverIp}:{serverPort}/profile/pics/attack_0545e131a67c4308a7a97a6cb25512f4.webp",
              "imgInfo": {
                  "racer": 10.39,
                  "car wheel": 1.29,
                  "convertible": 10.92,
                  "beach wagon": 3.01,
                  "sports car": 53.36
              }
          },
          "rimg": {
              "id": "22062011101085304b1850da",
              "url": "{serverIp}:{serverPort}/profile/pics/defense_attack_0545e131a67c4308a7a97a6cb25512f4.webp",
              "imgInfo": {
                  "racer": 35.35,
                  "convertible": 32.46,
                  "beach wagon": 9.97,
                  "pickup": 0.92,
                  "sports car": 4.3
              }
          }
      }
  }
  ```

---

### **API3：**

* 路由：/getRecentRecords

* 概述：对已上传于服务器上的图片进行处理，返回处理结果

* 方法：get

* 参数及说明：无

* 返回信息(JSON)：

  eg：

  ```json
  [
      {
          "id": "2206200839197eb7d8602879",
          "tag": "attack",
          "type": "attack",
          "createTime": "2022-06-20 00:00:00",
          "simg": {
              "id": "2206200839197eb7d8602879",
              "url": "{serverIp}:{serverPort}/profile/pics/0545e131a67c4308a7a97a6cb25512f4.webp",
              "imgInfo": {
                  "racer": 7.96,
                  "convertible": 23.92,
                  "beach wagon": 5.15,
                  "amphibian": 18.16,
                  "sports car": 14.87
              }
          },
          "rimg": {
              "id": "2206200839197eb7d8602879",
              "url": "{serverIp}:{serverPort}/profile/pics/attack_0545e131a67c4308a7a97a6cb25512f4.webp",
              "imgInfo": {
                  "racer": 10.39,
                  "car wheel": 1.29,
                  "convertible": 10.92,
                  "beach wagon": 3.01,
                  "sports car": 53.36
              }
          }
      },
      {
          "id": "220620085407a945223dde2c",
          "tag": "attack",
          "type": "CW",
          "createTime": "2022-06-20 00:00:00",
          "simg": {
              "id": "220620085407a945223dde2c",
              "url": "{serverIp}:{serverPort}/profile/pics/attack_0545e131a67c4308a7a97a6cb25512f4.webp",
              "imgInfo": {
                  "racer": 10.39,
                  "car wheel": 1.29,
                  "convertible": 10.92,
                  "beach wagon": 3.01,
                  "sports car": 53.36
              }
          },
          "rimg": {
              "id": "220620085407a945223dde2c",
              "url": "{serverIp}:{serverPort}/profile/pics/attack_CW_attack_0545e131a67c4308a7a97a6cb25512f4.webp",
              "imgInfo": {
                  "racer": 14.36,
                  "convertible": 13.7,
                  "beach wagon": 5.99,
                  "amphibian": 8.76,
                  "sports car": 14.9
              }
          }
      },
      {
          "id": "2206200856044e937d6576d3",
          "tag": "attack",
          "type": "FGSM",
          "createTime": "2022-06-20 00:00:00",
          "simg": {
              "id": "2206200856044e937d6576d3",
              "url": "{serverIp}:{serverPort}/profile/pics/attack_0545e131a67c4308a7a97a6cb25512f4.webp",
              "imgInfo": {
                  "racer": 10.39,
                  "car wheel": 1.29,
                  "convertible": 10.92,
                  "beach wagon": 3.01,
                  "sports car": 53.36
              }
          },
          "rimg": {
              "id": "2206200856044e937d6576d3",
              "url": "{serverIp}:{serverPort}/profile/pics/attack_FGSM_attack_0545e131a67c4308a7a97a6cb25512f4.webp",
              "imgInfo": {
                  "racer": 34.26,
                  "car wheel": 1.46,
                  "convertible": 1.55,
                  "sports car": 47.85,
                  "Band Aid": 0.9
              }
          }
      }
  ]
  ```
  ---

### **API4：**

* 路由：/getRecentResRecords

* 概述：对已上传于服务器上的图片进行处理，返回处理结果

* 方法：get

* 参数及说明：无

* 返回信息(JSON)：

  eg:

  ```json
  [
      {
          "id": "2206200839197eb7d8602879",
          "tag": "attack",
          "type": "attack",
          "createTime": "2022-06-20 00:00:00",
          "rimg": {
              "id": "2206200839197eb7d8602879",
              "url": "{serverIp}:{serverPort}/profile/pics/attack_0545e131a67c4308a7a97a6cb25512f4.webp",
              "imgInfo": {
                  "car wheel": 1.29
              }
          }
      },
      {
          "id": "220620085407a945223dde2c",
          "tag": "attack",
          "type": "CW",
          "createTime": "2022-06-20 00:00:00",
          "rimg": {
              "id": "220620085407a945223dde2c",
              "url": "{serverIp}:{serverPort}/profile/pics/attack_CW_attack_0545e131a67c4308a7a97a6cb25512f4.webp",
              "imgInfo": {
                  "beach wagon": 5.99
              }
          }
      },
      {
          "id": "2206200856044e937d6576d3",
          "tag": "attack",
          "type": "FGSM",
          "createTime": "2022-06-20 00:00:00",
          "rimg": {
              "id": "2206200856044e937d6576d3",
              "url": "{serverIp}:{serverPort}/profile/pics/attack_FGSM_attack_0545e131a67c4308a7a97a6cb25512f4.webp",
              "imgInfo": {
                  "Band Aid": 0.9
              }
          }
      }
  ]
  ```
