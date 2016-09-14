# Geolocation API介绍

* Geolocation API用于将用户当前地理位置信息共享给信任的站定

* Geolocation API位于navigator对象中，只有三个方法

  * getCurrentPosition\(\)

  * watchPositon\(\)

  * clearWatch\(\)



# getCurrentPositon

```
   navigator.geolocation.getCurrentPositon(success_callBack,error_callBack,{ggeolocation选项})
```

* success\_callBack:用户允许共享geolocation的回调

* error.callBack：获取地理位置失败的回调，传入错误对象，包含code,message属性

* 选项 
  **enableHighAccuracy:是否更精确读取经纬度，默认false**

```

navigator.geolocation.getCurrentPosition\(function\(position\)\){  }）
```

- position的属性

  - coords
  - latitude：当前位置的维度
  - longitude：当前位置的经度

  - altitude：海拔，海平面以上以米计
  - speed:速度，以米/秒计

