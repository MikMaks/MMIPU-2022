# Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`class `[`LinearMod`](#class_linear_mod) | Класс, представляющий линейную модель контролируемого объекта
`class `[`Model`](#classModel) | Абстрактный класс, который будет использоваться для построения линейных и нелинейных моделей
`class `[`NonLinearMod`](#class_non_linear_mod) | Класс, представляющий нелинейную модель контролируемого объекта
`class `[`Regulator`](#classRegulator) | Класс для реализации регулятора

## class `LinearMod` 

```
class LinearMod
  : public Model
```

Класс, представляющий линейную модель контролируемого объекта

Дочерний класс, который расширяет класс model

### Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public inline  `[`LinearMod`](#class_linear_mod_1a75f89a870b01deb52c0885435ae57c4e)`(float a, float b, float y_t1)` | конструктор для [LinearMod](#class_linear_mod)
`public inline virtual float `[`equation`](#class_linear_mod_1a381674509c44cabf43ca6ba062675dea)`(float y_t, float u_t)` | функция для вычисления температуры по линейной модели


### Members

#### `public inline  `[`LinearMod`](#class_linear_mod_1a75f89a870b01deb52c0885435ae57c4e)`(float a, float b, float y_t1)` 

конструктор для [LinearMod](#class_linear_mod)
#### Parameters
* `a` `b` - просто коэффициенты 

* `y_t1` - температура на выходе

#### `public inline virtual float `[`equation`](#class_linear_mod_1a381674509c44cabf43ca6ba062675dea)`(float y_t, float u_t)` 

функция для вычисления температуры по линейной модели

## class `Model` 

Абстрактный класс, который будет использоваться для построения линейных и нелинейных моделей

### Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public float `[`equation`](#classmodel_1a11867c371c659577519db1fe627dac59)`(float y_t, float u_t)` | абстрактная функция для переопределения в дочерних классах

### Members

#### `public float `[`equation`](#classmodel_1a11867c371c659577519db1fe627dac59)`(float y_t, float u_t)` 

абстрактная функция для переопределения в дочерних классах

## class `NonLinearMod`

```
class NonLinearMod
  : public Model
```

Класс, представляющий нелинейную модель контролируемого объекта

Дочерний класс, который расширяет класс model

### Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public inline  `[`NonLinearMod`](#class_non_linear_mod_1abdc835f56120ccc4d4eb7a3d3c60314c)`(float a, float b, float c, float d, float y_t1)` | конструктор для [NonLinearMod](#class_non_linear_mod)
`public inline virtual float `[`equation`](#class_non_linear_mod_1ab5d708bdcc976c5ab1196322b9d32829)`(float y_t, float u_t)` | функция для вычисления температуры по нелинейной модели


### Members

#### `public inline  `[`NonLinearMod`](#class_non_linear_mod_1abdc835f56120ccc4d4eb7a3d3c60314c)`(float a, float b, float c, float d, float y_t1)` 

конструктор для [NonLinearMod](#class_non_linear_mod)
#### Parameters
* `a` `b` `c` `d` просто коэффициенты

#### `public inline virtual float `[`equation`](#class_non_linear_mod_1ab5d708bdcc976c5ab1196322b9d32829)`(float y_t, float u_t)` 

функция для вычисления температуры по нелинейной модели

## class `Regulator`

Класс для реализации регулятора

### Summary

 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
`public inline  `[`Regulator`](#classregulator_1a7c40ac8810c3d6a4cd583b011d673f78)`(float T, float T0, float TD, float K)` | конструктор для Regulator 
`public inline float `[`temperature`](#classregulator_1a54bc0b1a0c02beb98ff634b9acc91876)`(float e, float em1, float em2)` | функция для подсчёта управляющей переменной 


### Members

#### `public inline  `[`regulator`](#classRegulator_1a7c40ac8810c3d6a4cd583b011d673f78)`(float T, float T0, float TD, float K)` 

конструктор для regulator 
#### Parameters
* `K` `T0` `TD` `T` слева-направо: коэффициент передачи, шаг, постоянная диференцирования, постоянная интегрирования

#### `public inline float `[`temperature`](#classRegulator_1a54bc0b1a0c02beb98ff634b9acc91876)`(float e, float em1, float em2)`

функция для подсчёта управляющей переменной 
#### Parameters
* `e` `em1` `em2` значения текущей, прошлой и позапрошлой ошибок