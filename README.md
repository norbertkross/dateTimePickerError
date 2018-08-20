# dateTimePickerError
  
  Future<Null> datefunc(BuildContext context) async{
    final DateTime yrchoice = await showDatePicker(
        context: context,
        initialDate: theDate,
        firstDate: new DateTime(2018),
        lastDate:new DateTime(2030) );
    if(yrchoice !=null && yrchoice != theDate){
      setState(() {
        theDate = yrchoice;
      });

    }

  }
  
            ExpansionTile(
          initiallyExpanded: true,
                  backgroundColor: Colors.green,
                  title:Container(
                    color: Colors.yellow,
                    child: Row(
                    children: <Widget>[
                      Icon(Icons.calendar_today),
                      // Icon(IconData(0xF4CA,
                      // fontFamily: 'CupertinoIcons'
                      // )),
                      Text('  Date')
                    ],
                  ),
                  ),
                  children: <Widget>[
                    Column(
                      children: <Widget>[
                              FittedBox(
                              fit: BoxFit.contain,
                              child:  Row(
                          children: <Widget>[
                  CupertinoButton(
                color: CupertinoColors.activeBlue,
                child:Text('From'),
                //Icon(Icons.access_time),
                onPressed: (){datefunc( context);},
              ),
              Text('${DateFormat('EEE dd MMM').format(theDate).toString()}')
                          ],
                        ),
                            ),

                      ],
                    ),
                  ],

          ),
