# ================================
# Project: IdeaForge 
# Description:
# A workshop of big ideas — crafting resilient software,
# testing new technologies, and building projects that endure.
# ================================

# ---------- main.py ----------
"""
Main entry point for IdeaForge.
"""

from core import work, durability


def run():
    print("🛠️  Welcome to IdeaForge")
    print("🚀 Big Ideas | 🔬 New Technologies | 🧱 Resilient Code\n")

    # Demo features
    idea = "Resilient Design"
    print(f"💡 Forged Idea Summary: {workshop.summarize_idea(idea)}")
    print(f"🔁 Tech Test (Simulated Network Request): {workshop.simulate_request('https://example.com')}")
    print(f"🧩 Durability Score: {durability.stress_test([1, 2, 3, 4, 5])}")


if __name__ == "__main__":
    run()


# ---------- core/workshop.py ----------
"""
Module for experimentation and testing of new technologies.
"""

import random
import time

def summarize_idea(idea: str) -> str:
    """Summarize an idea creatively."""
    return f"'{idea}' represents innovation, resilience, and forward thinking."

def simulate_request(url: str) -> str:
    """Simulate a network request (for testing resilience)."""
    print(f"🔧 Connecting to {url}...")
    time.sleep(0.5)
    if random.random() < 0.8:
        return "✅ Connection successful."
    else:
        return "❌ Connection failed."


# ---------- core/durability.py ----------
"""
Module for building resilient, long-lasting software components.
"""

import statistics

def stress_test(data):
    """
    Simulate a stress test on a system's load handling.
    Returns a 'durability score' based on data variance.
    """
    if not data:
        return 0
    mean = statistics.mean(data)
    stdev = statistics.pstdev(data)
    score = round((mean / (1 + stdev)) * 10, 2)
    return score

def reinforce_system(params: dict) -> dict:
    """Increase reliability by adjusting system parameters."""
    return {k: round(v * 1.1, 2) for k, v in params.items()}


# ---------- tests/test_durability.py ----------
"""
Tests for durability.py
Run with: pytest
"""

from core import durability

def test_stress_test():
    score = durability.stress_test([1, 2, 3, 4, 5])
    assert score > 0

def test_reinforce_system():
    params = {"speed": 10, "stability": 20}
    reinforced = durability.reinforce_system(params)
    assert reinforced["speed"] == 11.0
    assert reinforced["stability"] == 22.0
