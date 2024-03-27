# AI-powered-Fitness-Coach
开发一款AI驱动的健身教练应用程序，根据用户的目标和进度提供个性化的锻炼计划和反馈。
class FitnessCoach:
    def __init__(self):
        self.users = {}

    def create_user_profile(self, username, age, weight, goal):
        self.users[username] = {
            "age": age,
            "weight": weight,
            "goal": goal,
            "workout_plan": None,
            "progress": []
        }
        self.generate_workout_plan(username)

    def generate_workout_plan(self, username):
        user = self.users[username]
        goal = user["goal"]
        
        # Simplified plan generation logic
        if goal == "weight loss":
            plan = ["30 mins cardio", "15 mins strength training", "5 mins stretching"]
        elif goal == "muscle gain":
            plan = ["10 mins cardio", "40 mins strength training", "10 mins stretching"]
        elif goal == "endurance":
            plan = ["45 mins cardio", "15 mins strength training", "5 mins stretching"]
        else:
            plan = ["20 mins cardio", "20 mins strength training", "5 mins stretching"]
        
        user["workout_plan"] = plan

    def log_progress(self, username, progress):
        self.users[username]["progress"].append(progress)
        self.provide_feedback(username, progress)

    def provide_feedback(self, username, progress):
        print(f"Great job, {username}! Keep up the good work!")
        # Implement logic for personalized feedback based on progress

    def get_workout_plan(self, username):
        return self.users[username]["workout_plan"]

# Example usage
coach = FitnessCoach()
coach.create_user_profile("JohnDoe", 30, 70, "weight loss")
print(coach.get_workout_plan("JohnDoe"))
coach.log_progress("JohnDoe", "Completed day 1 workout")
