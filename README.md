DOWNLOAD
========

project build.gradle:
```
allprojects {
  repositories {
    ...
    maven { url 'https://jitpack.io' }
  }
}
```

module build.gradle:
```
dependencies {
  compile 'com.github.pandyin:rxrealm:1.1.2'
}
```



USAGE
========

- [RealmObject](https://realm.io/docs/java/4.3.3/api/io/realm/RealmObject.html) must have ```@RxRealm``` annotation

- [RealmObject](https://realm.io/docs/java/4.3.3/api/io/realm/RealmObject.html) must define a primary key by using ```@PrimaryKey```

example:

```
@RxRealm
public class Car extends RealmObject {

    @PrimaryKey
    private String id;
    private String color;
    private int model;
```



GENERATED CLASS
========

...



OPERATIONS
========

get operation:
--------

```fieldName + OperationName```

- example:

```
RxCar.get().idEqualTo(id) //condition
              .colorEqualTo(color)  //condition
              .modelGreaterThan(model) //condition
              .getAysnc(); //execute
```

- condition operations:

```equalTo```

```notEqualTo```

```in```

```notIn```

```lessThan```

```greaterThan```

```sortBy```

```or```

```edit```

```first```

- execute operations:

```getAysnc```

```deleteAsync```

```countAsync```

set operation:
--------

```OperationName + fieldName```

- example:

```
RxCar.set(id)
        .setColor(pink)
        .setModel(2019)
        .setAsync(); //execute
```

- operation:

```set```

- execute operations:

```setAsync```


EXAMPLE
========

[MainActivity.java](https://github.com/pandyin/rxrealm/blob/master/example/src/main/java/com/intathep/android/rxrealm/MainActivity.java)
