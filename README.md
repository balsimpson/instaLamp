# instaLamp
A Lamp that shows the current palette of a user specified instagram post

	thinger
	//testing
	/* Set up over the air updating of the controller */
	ota

	/* Set the mode for the lamp */
	lamp mode
    //palette mode - single hue with slight movement
    //transition mode - a flash to notify transition
    //notification mode - depending on the notification mode	

	/* Set the led animation for the lamp */
	led animation
    //palette mode
    change palette periodically

    //transition
    play transition once

    //notification
      service - twitter/instagram/facebook/ifttt
      user - rumina, garima, anoop



	/* Set the palettes */
	palettes
    //create new palettes

    //define set palettes
    void staticPalettes() {
      //van gogh
        //starry night
        CRGBPalette16 StarryNight = (CRGB(39,83,89), 39,63,65, 54,116,125, 71,99,75, 136,136,91)

    }

    // instagram post palette


	/* Check and log sensor data */
	sensor data
    //every 30 secs log data
    temp sensor
    ldr
    mic
      //global variable
      int soundPin = A0;
      const int numReadings = 30;
      int soundReadings[numReadings];      // the readings from the input
      int readIndex = 0;                   // the index of the current reading
      int soundTotal = 0;                  // the running total
      int soundAverage = 0;                // the average

      //average
      soundTotal = soundTotal - soundReadings[readIndex];
      soundReadings[readIndex] = digitalRead(soundPin);
      soundTotal = soundTotal + soundReadings[readIndex];
      readIndex = readIndex + 1;

      if (readIndex >= numReadings) {
        readIndex = 0;
      }
      soundAverage = soundTotal / numReadings;

    pir
    mq7
    accelerometer
      dance if shaking detected
    tweet
