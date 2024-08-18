# Toyota-Camryclass ToyotaCamry:
    def __init__(self):
        self.engine_running = False
        self.speed = 0

    def start_engine(self):
        if not self.engine_running:
            self.engine_running = True
            print("Engine started.")
        else:
            print("Engine is already running.")

    def stop_engine(self):
        if self.engine_running:
            if self.speed == 0:
                self.engine_running = False
                print("Engine stopped.")
            else:
                print("You need to stop the car before turning off the engine.")
        else:
            print("Engine is already off.")

    def accelerate(self, increment):
        if self.engine_running:
            self.speed += increment
            print(f"Accelerating. Current speed: {self.speed} km/h")
        else:
            print("Can't accelerate. The engine is off.")

    def brake(self, decrement):
        if self.engine_running and self.speed > 0:
            self.speed -= decrement
            if self.speed < 0:
                self.speed = 0
            print(f"Braking. Current speed: {self.speed} km/h")
        else:
            print("Car is already stopped or the engine is off.")

    def get_status(self):
        engine_status = "running" if self.engine_running else "off"
        print(f"Engine: {engine_status}, Speed: {self.speed} km/h")


# Example usage:
camry = ToyotaCamry()

camry.get_status()
camry.start_engine()
camry.accelerate(20)
camry.brake(10)
camry.get_status()
camry.stop_engine()
