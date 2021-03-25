# flutter-swipping-button
[![Platform](https://img.shields.io/badge/platform-android%20|%20ios-green.svg)](https://img.shields.io/badge/platform-Android%20%7C%20iOS-green.svg)

A simple animated swipping button for flutter


## Usage

Here is a quick example of the button implemented in this example app:

```dart
Center(
      //Container for the button. Here you can set how the button would be like.
      child: Column(
        mainAxisAlignment: MainAxisAlignment.center,
        children: <Widget>[
          Container(
            width: MediaQuery.of(context).size.width,
            padding: EdgeInsets.fromLTRB(10, 0, 10, 0),
            child: Stack(
              children: <Widget>[
                Container(
                  height: 80.0,
                  decoration: BoxDecoration(
                      color: Colors.green,
                      borderRadius: BorderRadius.circular(4.0)),
                      //Set the background (after the swipe, this will be shown)
                  child: _swipeButtonBackgroundWidget,
                ),
                //Swippable Button
                SwipableButton(
                  height: 80.0,
                  delay: Duration(seconds: 3), 
                  returnToInitialPosition: true, //If is true, the button will be set at original position after the delay
                  child: Container(
                    child: Padding(
                      padding: const EdgeInsets.fromLTRB(16, 0, 16, 0),
                      child: Container(
                        child: Row(
                            mainAxisAlignment: MainAxisAlignment.spaceBetween,
                            children: [
                              Text(
                                "Swipe to Open",
                                overflow: TextOverflow.fade,
                                style: TextStyle(
                                    color: Colors.white,
                                    fontWeight: FontWeight.bold,
                                    fontSize:
                                        MediaQuery.of(context).size.width *
                                            0.035),
                              ),
                              Container(
                                  child: Icon(Icons.navigate_next,
                                      color: Colors.white)),
                            ]),
                      ),
                    ),
                    //Initial swipe button decoration
                    height: 80.0,
                    decoration: BoxDecoration(
                        color: Colors.red,
                        borderRadius: BorderRadius.circular(4.0)),
                  ),
                  onSwipeCallback: _onSwipeCallback, //Action if you complete the swipe
                ),
              ],
            ),
          ),
        ],
      ),
    );
```


