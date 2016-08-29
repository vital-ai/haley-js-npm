Haley JS Client
=========

Haley JS Client Library to communicate with Haley AI service

## Installation

  `npm install @vital-ai/haley`

## Usage

    var haleyModule = require('@vital-ai/haley');
    
    var VitalService = haleyModule.VitalService;
    var HaleyAPI = haleyModule.HaleyAPI;
    var HaleyAPIVitalServiceImpl = haleyModule.HaleyAPIVitalServiceImpl;
    
    var APP_ID = ...;
    
    var ENDPOINT = 'endpoint.' + APP_ID;
    
    var EVENTBUS_URL = 'https://haley-ai-login.vital.ai/eventbus';

    var _vitalservice = new VitalService(ENDPOINT, EVENTBUS_URL, function(){

      console.log('connected to endpoint, sessionID: ' + _vitalservice.impl.sessionID);

      var impl = new HaleyAPIVitalServiceImpl(_vitalservice);

      new HaleyAPI(impl, false, function(error, instance){

        if(error) {
          //handle error
        }

        console.log("haley api ready for action");

        onHaleyAPIReady();

      });

    }, function(error){

      console.error('couldn\'t connect to endpoint -' + error);
		
	});
    


## Tests

  `npm test`

## Contributing


