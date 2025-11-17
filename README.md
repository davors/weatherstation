# weatherstation
Package weather provides a simulated weather station that generates random weather data.

The package implements a concurrent weather station that runs three independent sensors
(temperature, humidity, and pressure) as goroutines. Each sensor generates random
measurements at configurable intervals and sends them through a shared channel.

Example usage:

station := weather.NewStation(1*time.Second, 5*time.Second)
defer station.Stop()

data, err := station.GetData()
if err != nil {
		log.Fatal(err)
	}
fmt.Printf("Type: %s, Value: %.2f\n", data.MType, data.Value)

The weather station generates the following measurements:
  - Temperature: -5-30°C
  - Humidity: 40-80%
  - Pressure: 950-1010 mbar
