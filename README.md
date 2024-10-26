# devcontainer_cafeobj

## Why
cafeobj は x86 binary で配ってたりしているので、残念ながら直接 Apple siliconなMacとかで動かせたりしない。なのでself buildしてdevcontainer 上で動かせるようにする

## buildの仕方
cf. [https://cafeobj.org/2015/02/tutorial-first-steps-in-cafeobj/](https://cafeobj.org/2015/02/tutorial-first-steps-in-cafeobj/)
```shell
cafeobj -batch src/sample_fnc.cafe > cafe.out　
```

## 参考
- CafeOBJ自体とかはこの辺を見ると便利
  - http://www.jaist.ac.jp/~ogata/lecture/tokyo-i217/
  - https://cafeobj.org/intro/ja/
