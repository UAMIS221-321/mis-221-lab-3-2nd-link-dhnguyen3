using System;

public class CollegeFootballIntro
{
    public static void Main(string[] args)
    {
        string enjoymentLevel = GetEnjoymentLevel();
        string stadium = GetStadiumRecommendation(enjoymentLevel);
        string game = GetGameRecommendation(stadium);
        DisplayStadiumDetails(stadium, game);
    }

    public static string GetEnjoymentLevel()
    {
        Console.WriteLine("What level of enjoyment are you looking for? (Boring, Average, Fun, Epic): ");
        string enjoymentLevel = Console.ReadLine().Trim().ToLower();

        while (!IsValidEnjoymentLevel(enjoymentLevel))
        {
            Console.WriteLine("Invalid level. Please enter Boring, Average, Fun, or Epic: ");
            enjoymentLevel = Console.ReadLine().Trim().ToLower();
        }

        return enjoymentLevel;
    }

    public static bool IsValidEnjoymentLevel(string enjoymentLevel)
    {
        return enjoymentLevel == "boring" || enjoymentLevel == "average" || enjoymentLevel == "fun" || enjoymentLevel == "epic";
    }

    public static string GetStadiumRecommendation(string enjoymentLevel)
    {
        switch (enjoymentLevel)
        {
            case "boring":
                return "Neyland Stadium";
            case "average":
                return "Jordan-Hare Stadium";
            case "fun":
                return "Tiger Stadium";
            case "epic":
                return "Saban Field at Bryant-Denny Stadium";
            default:
                return "Invalid enjoyment level"; // This shouldn't happen due to validation in GetEnjoymentLevel
        }
    }

    public static string GetGameRecommendation(string stadium)
    {
        switch (stadium)
        {
            case "Neyland Stadium":
                return "vs Kent State";
            case "Jordan-Hare Stadium":
                return "vs Kentucky";
            case "Tiger Stadium":
                return "vs Alabama";
            case "Saban Field at Bryant-Denny Stadium":
                return "vs Auburn";
            default:
                return "Invalid stadium"; // This shouldn't happen due to logic in GetStadiumRecommendation
        }
    }

    public static void DisplayStadiumDetails(string stadium, string game)
    {
        Console.WriteLine($"For the best {stadium} experience, we recommend attending the {game} game!");
    }
}
