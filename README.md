import random

def monty_hall_simulation(num_simulations):
    wins_without_switching = 0
    wins_with_switching = 0

    for _ in range(num_simulations):
        doors = ['car', 'goat', 'goat']  
        for i in range(3):
            if i != your_choice and doors[i] == 'goat':
                monty_opens = i
                break

        for i in range(3):
            if i != your_choice and i != monty_opens:
                your_choice = i
                break

        if doors[your_choice] == 'car':
            wins_with_switching += 1
        else:
            wins_without_switching += 1

    return wins_with_switching, wins_without_switching

if __name__ == "__main__":
    num_simulations = int(input("enter the value:"))  
    wins_with_switching, wins_without_switching = monty_hall_simulation(num_simulations)
    print(f"Simulations: {num_simulations}")
    print(f"Wins with switching: {wins_with_switching}")
    print(f"Wins without switching: {wins_without_switching}")
    print(f"Probability of winning with switching: {wins_with_switching / num_simulations:.4f}")
    print(f"Probability of winning without switching: {wins_without_switching / num_simulations:.4f}")
