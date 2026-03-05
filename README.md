# Rewards-puzzle-game
Rewards puzzle game solve then win money and earn money 
Colors.blueimport 'package:flutter/material.dart';
import 'home_screen.dart';

void main() {
  runApp(const PuzzleRewardsApp());
}

class PuzzleRewardsApp extends StatelessWidget {
  const PuzzleRewardsApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Puzzle Rewards Game',
      theme: ThemeData(primarySwatch: Colors.blue),
      home: const HomeScreen(),
    );
  }
}import 'package:flutter/material.dart';
import 'puzzle_game.dart';

class HomeScreen extends StatelessWidget {
  const HomeScreen({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: const Text("Puzzle Rewards Game")),
      body: Center(
        child: ElevatedButton(
          child: const Text("Play Puzzle Game"),
          onPressed: () {
            Navigator.push(
              context,
              MaterialPageRoute(builder: (context) => const PuzzleGame()),
            );
          },
        ),
      ),
    );
  }
}import 'package:flutter/material.dart';
import 'reward_system.dart';

class PuzzleGame extends StatefulWidget {
  const PuzzleGame({super.key});

  @override
  State<PuzzleGame> createState() => _PuzzleGameState();
}

class _PuzzleGameState extends State<PuzzleGame> {

  int score = 0;

  void solvePuzzle() {
    setState(() {
      score += 10;
    });

    RewardSystem.addReward(10);
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: const Text("Puzzle Game")),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: [

            Text("Score: $score",
            style: const TextStyle(fontSize: 24)),

            const SizedBox(height: 20),

            ElevatedButton(
              onPressed: solvePuzzle,
              child: const Text("Solve Puzzle"),
            ),
          ],
        ),
      ),
    );
  }
}MainAxisAlignment.centerPuzzle Rewards Game

This is a Flutter mobile game project where users solve puzzles and earn reward coins.

Features
- Puzzle solving game
- Reward coins system
- Expandable for Ludo / Carrom games
- Future wallet and withdraw systemclass RewardSystem {

  static int totalCoins = 0;

  static void addReward(int coins) {
    totalCoins += coins;
    print("User earned $coins coins");
  }

}


















