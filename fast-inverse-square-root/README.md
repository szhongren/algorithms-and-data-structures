# fast inverse square root

original code in Quake

```
float FastInvSqrt(float x) {
  float xhalf = 0.5f * x;
  int i = *(int*)&x;         // evil floating point bit level hacking
  i = 0x5f3759df - (i >> 1);  // what the fuck?
  x = *(float*)&i;
  x = x*(1.5f-(xhalf*x*x));
  return x;
}
```

works by using a linear function to approximate log_2(1 + x) from 0 to 1

[full details here](http://h14s.p5r.org/2012/09/0x5f3759df.html)
