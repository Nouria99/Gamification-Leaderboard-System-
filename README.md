# Gamification-Leaderboard-System-
A MongoDB-based leaderboard and gamification system designed to track user progress, challenges, and badges in an educational platform.
Code

// 1. Insert Sample Users into “users” Collection
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
