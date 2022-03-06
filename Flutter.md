#                                                  Flutter 

## Widgets

![](https://github.com/KhalidOukssim/Guide/tree/main/Images/materialApp.JPG)



## main.dart

```dart
void main() => runApp(MainClass());
```

```dart
 Widget build(BuildContext context) {
    return MaterialApp(
      debugShowCheckedModeBanner: false,
      theme: ThemeData.themeName().copyWith(
        primaryColor: Color(0xFF******),
          //FF for الدقة
        scaffoldBackgroundColor: Color(0xFF******),
      ),
      home: Page1(),//className 
    );
  }
```

## pubspec.yaml

```yaml
flutter:

  uses-material-design: true

  assets:
    - images/
    - sounds/

```



## page1.dart

### how to declare a stateful Widget

```dart
class Page1 extends StatefulWidget {
  @override
  _Page1State createState() => _Page1State();
}
```

```dart
class _Page1State extends State<Page1>
```

### stateless vs stateful

### Scaffold

```dart
Widget build(BuildContext context) {
    return Scaffold(
        appBar: AppBar(
          title: Text(''),
        ),
        body:Column/Row/Center(
          crossAxisAlignment: CrossAxisAlignment.stretch,
          children: <Widget>[
            Expanded( //to respect the dimension of screen
                child:Column/Row/Center...
        ),
        );
```

## Create your own Widget

```dart
class WidgetName extends StatelessWidget {
  WidgetName({@required this.colour, this.childBMI, this.onPress});//your parameters & fcts
  final Widget childBMI;
  final Color colour;
  final Function onPress;
    //final VS const

  @override
  Widget build(BuildContext context) {
    return GestureDetector(
      onTap: onPress,
      child: Container(
        child: childBMI,
        margin: EdgeInsets.all(14.0),
        decoration: BoxDecoration(
          color: colour,
          borderRadius: BorderRadius.circular(10.0),
        ),
      ),
    );
  }
}
```

