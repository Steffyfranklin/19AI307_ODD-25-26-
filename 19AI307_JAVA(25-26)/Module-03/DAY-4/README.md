# Ex.No:3(D)    INTERFACE 

## QUESTION:
You are programming bots that analyze weather data. Each bot must implement a common interface and give a prediction.


 Bot Types:

SunBot: Predicts "HOT" if temperature > 30, else "MODERATE".

RainBot: Predicts "COLD" if temperature < 20, else "WARM".

Input:

temperature
botType (1 for SunBot, 2 for RainBot)Output:
Prediction as a string.

<img width="368" height="142" alt="Screenshot 2025-11-20 090521" src="https://github.com/user-attachments/assets/46adcfae-4fea-4b22-9bdd-d50a4e337185" />


## AIM:
To implement bots that analyze temperature data and predict weather conditions based on bot type and temperature input.

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Read temperature and bot type from input.
4. If bot type is SunBot (1):
5. Predict "HOT" if temperature > 30; otherwise, "MODERATE".
6. If bot type is RainBot (2):
7. Predict "COLD" if temperature < 20; otherwise, "WARM".
8. Print the prediction output.

## PROGRAM:
 ```
/*
Program to implement a Interface using Java
Developed by: STEFFY AAVLIN RAJ F S
RegisterNumber: 212224040330
*/
```

## SOURCE CODE:
```
import java.util.*;

interface WeatherBot {
    String predict(int temperature);
}

class SunBot implements WeatherBot {
    public String predict(int temperature) {
        return temperature > 30 ? "HOT" : "MODERATE";
    }
}

class RainBot implements WeatherBot {
    public String predict(int temperature) {
        return temperature < 20 ? "COLD" : "WARM";
    }
}

public class WeatherPrediction {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int temperature = sc.nextInt();
        int botType = sc.nextInt();

        WeatherBot bot;

        if (botType == 1) {
            bot = new SunBot();
        } else if (botType == 2) {
            bot = new RainBot();
        } else {
            bot = null;
        }

        if (bot != null) {
            System.out.println(bot.predict(temperature));
        } else {
            System.out.println("Invalid bot type");
        }

        sc.close();
    }
}
```
## OUTPUT:

<img width="907" height="293" alt="Screenshot 2025-11-20 090727" src="https://github.com/user-attachments/assets/05ab0cef-1fa8-4ac4-ae09-ce362ed4444f" />

## RESULT:
The program prints the weather prediction ("HOT", "MODERATE", "COLD", or "WARM") based on the temperature and bot type inputs, following the specified logic.
