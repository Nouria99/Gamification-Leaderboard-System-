# Gamification-Leaderboard-System-
A MongoDB-based leaderboard and gamification system designed to track user progress, challenges, and badges in an educational platform.
Code

// =====================================================
// 🎮 Gamification & Leaderboard System – Sample MongoDB Script
// Author: Nouria Bellamri
// Description: Insert sample data and perform key queries
// =====================================================

// 📥 1. Insert Sample Users into “users” Collection
db.users.insertMany([
  {
    user_id: "U001",
    username: "ZaraLearns",
    full_name: "Zara Khan",
    email: "zara@example.com",
    level: 3,
    points: 1270,
    badges: ["EarlyBird", "QuizMaster"],
    joined_date: ISODate("2024-02-15T00:00:00Z")
  },
  {
    user_id: "U002",
    username: "CodeNinja23",
    full_name: "Liam Patterson",
    email: "liam@example.com",
    level: 5,
    points: 1940,
    badges: ["ChallengeWinner", "Helper"],
    joined_date: ISODate("2023-12-10T00:00:00Z")
  },
  {
    user_id: "U003",
    username: "TinkerBelle",
    full_name: "Chloe Tan",
    email: "chloe@example.com",
    level: 2,
    points: 870,
    badges: ["EarlyBird"],
    joined_date: ISODate("2024-03-08T00:00:00Z")
  },
  {
    user_id: "U004",
    username: "DevDan",
    full_name: "Daniel Brown",
    email: "daniel@example.com",
    level: 4,
    points: 1510,
    badges: ["QuizMaster", "Mentor"],
    joined_date: ISODate("2024-01-22T00:00:00Z")
  },
  {
    user_id: "U005",
    username: "EcoLearner",
    full_name: "Sophie Green",
    email: "sophie@example.com",
    level: 1,
    points: 460,
    badges: [],
    joined_date: ISODate("2024-04-15T00:00:00Z")
  }
]);

// 📥 2. Insert Activity Logs into “activities” Collection
db.activities.insertMany([
  {
    activity_id: "A1001",
    user_id: "U001",
    activity_type: "quiz",
    description: "Scored 85% in 'Digital Literacy Basics' quiz",
    points_earned: 120,
    activity_date: ISODate("2024-04-01T00:00:00Z")
  },
  {
    activity_id: "A1002",
    user_id: "U002",
    activity_type: "challenge",
    description: "Participated in '30-Day Coding Sprint'",
    points_earned: 300,
    activity_date: ISODate("2024-03-15T00:00:00Z")
  },
  {
    activity_id: "A1003",
    user_id: "U003",
    activity_type: "quiz",
    description: "Scored 92% in 'Cyber Safety Basics' quiz",
    points_earned: 150,
    activity_date: ISODate("2024-04-10T00:00:00Z")
  },
  {
    activity_id: "A1004",
    user_id: "U004",
    activity_type: "challenge",
    description: "Won 1st place in 'Weekly Web Dev Challenge'",
    points_earned: 500,
    activity_date: ISODate("2024-03-25T00:00:00Z")
  },
  {
    activity_id: "A1005",
    user_id: "U005",
    activity_type: "quiz",
    description: "Completed 'Intro to Spreadsheets' quiz",
    points_earned: 90,
    activity_date: ISODate("2024-04-12T00:00:00Z")
  }
]);

// 📥 3. Insert Badges into “badges” Collection
db.badges.insertMany([
  {
    badge_id: "B001",
    name: "EarlyBird",
    description: "First module completed within 24 hours",
    points_required: 0,
    category: "Time-Based",
    created_date: ISODate("2024-01-01T00:00:00Z")
  },
  {
    badge_id: "B002",
    name: "QuizMaster",
    description: "Scored above 90% in any quiz",
    points_required: 100,
    category: "Achievement",
    created_date: ISODate("2024-01-10T00:00:00Z")
  },
  {
    badge_id: "B003",
    name: "ChallengeWinner",
    description: "Top 3 in any challenge",
    points_required: 250,
    category: "Competition",
    created_date: ISODate("2024-02-05T00:00:00Z")
  },
  {
    badge_id: "B004",
    name: "Helper",
    description: "Assisted others in forum discussions",
    points_required: 50,
    category: "Community",
    created_date: ISODate("2024-02-20T00:00:00Z")
  },
  {
    badge_id: "B005",
    name: "Mentor",
    description: "Helped 5+ learners or ran a peer session",
    points_required: 200,
    category: "Community",
    created_date: ISODate("2024-03-01T00:00:00Z")
  }
]);

// 📥 4. Insert Challenges into “challenges” Collection
db.challenges.insertMany([
  {
    challenge_id: "C001",
    name: "30-Day Coding Sprint",
    description: "Earn max points by completing daily tasks over 30 days.",
    start_date: ISODate("2024-03-01T00:00:00Z"),
    end_date: ISODate("2024-03-30T00:00:00Z"),
    type: "national",
    reward_points: 300
  },
  {
    challenge_id: "C002",
    name: "Weekly Web Dev Challenge",
    description: "Build a webpage in 7 days. Points for creativity.",
    start_date: ISODate("2024-03-20T00:00:00Z"),
    end_date: ISODate("2024-03-27T00:00:00Z"),
    type: "local",
    reward_points: 150
  },
  {
    challenge_id: "C003",
    name: "Digital Skills Marathon",
    description: "Complete 5 modules and 3 quizzes in 2 weeks.",
    start_date: ISODate("2024-04-01T00:00:00Z"),
    end_date: ISODate("2024-04-14T00:00:00Z"),
    type: "national",
    reward_points: 400
  },
  {
    challenge_id: "C004",
    name: "Spring Learner Showdown",
    description: "Earn most points this season across all activities.",
    start_date: ISODate("2024-09-01T00:00:00Z"),
    end_date: ISODate("2024-11-30T00:00:00Z"),
    type: "national",
    reward_points: 500
  }
]);

// 📥 5. Insert Leaderboards into “leaderboards” Collection
db.leaderboards.insertMany([
  {
    leaderboard_id: "L001",
    challenge_id: "C001",
    scope: "national",
    generated_on: ISODate("2024-04-01T00:00:00Z"),
    entries: [
      { user_id: "U002", username: "CodeNinja23", points: 300, rank: 1 },
      { user_id: "U004", username: "DevDan", points: 250, rank: 2 },
      { user_id: "U001", username: "ZaraLearns", points: 120, rank: 3 }
    ]
  },
  {
    leaderboard_id: "L002",
    challenge_id: "C002",
    scope: "local",
    generated_on: ISODate("2024-03-28T00:00:00Z"),
    entries: [
      { user_id: "U004", username: "DevDan", points: 500, rank: 1 },
      { user_id: "U003", username: "TinkerBelle", points: 150, rank: 2 }
    ]
  },
  {
    leaderboard_id: "L003",
    challenge_id: "C003",
    scope: "national",
    generated_on: ISODate("2024-04-15T00:00:00Z"),
    entries: [
      { user_id: "U002", username: "CodeNinja23", points: 350, rank: 1 },
      { user_id: "U001", username: "ZaraLearns", points: 300, rank: 2 },
      { user_id: "U005", username: "EcoLearner", points: 90, rank: 3 }
    ]
  }
]);

// =====================================================
// 🔍 Query Examples
// =====================================================

// 1. Top 3 Learners in a Specific Challenge
db.leaderboards.aggregate([
  { $match: { "challenge_id": "C001" } },
  { $project: {
      _id: 0,
      challenge_id: 1,
      entries: { $slice: ["$entries", 3] }
  }}
]);

// 2. View Badges Earned by a User
db.users.find(
  { "user_id": "U001" },
  { "_id": 0, "username": 1, "badges": 1 }
);

// 3. View All Activities by a User Sorted by Date
db.activities.find(
  { "user_id": "U002" }
).sort({ "activity_date": -1 });

// 4. Find High Scoring Learners
db.users.find(
  { "points": { "$gt": 1000 } },
  { "_id": 0, "username": 1, "points": 1 }
);

// 5. Find All Users Who Earned a Specific Badge
db.users.find(
  { "badges": "ChallengeWinner" },
  { "_id": 0, "username": 1, "badges": 1 }
);

// 6. Total Points Earned by a User from Activities
db.activities.aggregate([
  { $match: { user_id: "U001" } },
  { $group: {
      _id: "$user_id",
      total_points: { $sum: "$points_earned" }
  }}
]);
