<h1>ExpNo 5 : Implement Simple Hill Climbing Algorithm</h1> 
<h3>Name: V.S.Sree Viveka           </h3>
<h3>Register Number: 2305001031           </h3>
<H3>Aim:</H3>
<p>Implement Simple Hill Climbing Algorithm and Generate a String by Mutating a Single Character at each iteration </p>
<h2> Theory: </h2>
<p>Hill climbing is a variant of Generate and test in which feedback from test procedure is used to help the generator decide which direction to move in search space.
Feedback is provided in terms of heuristic function
</p>


<h2>Algorithm:</h2>
<p>
<ol>
 <li> Evaluate the initial state.If it is a goal state then return it and quit. Otherwise, continue with initial state as current state.</li> 
<li>Loop until a solution is found or there are no new operators left to be applied in current state:
<ul><li>Select an operator that has not yet been applied to the current state and apply it to produce a new state</li>
<li>Evaluate the new state:
  <ul>
<li>if it is a goal state, then return it and quit</li>
<li>if it is not a goal state but better than current state then make new state as current state</li>
<li>if it is not better than current state then continue in the loop</li>
    </ul>
</li>
</ul>
</li>
</ol>

</p>
<hr>
<h3> Steps Applied:</h3>
<h3>Step-1</h3>
<p> Generate Random String of the length equal to the given String</p>
<h3>Step-2</h3>
<p>Mutate the randomized string each character at a time</p>
<h3>Step-3</h3>
<p> Evaluate the fitness function or Heuristic Function</p>
<h3>Step-4:</h3>
<p> Lopp Step -2 and Step-3  until we achieve the score to be Zero to achieve Global Minima.</p>

## PROGRAM
```python
import random
import string

def generate_random_solution(answer):
    l = len(answer)
    return [random.choice(string.printable) for _ in range(l)]

def evaluate(solution, answer):
    print(solution)
    target = list(answer)
    diff = 0
    for i in range(len(target)):
        s = solution[i]
        t = target[i]
        # Calculate absolute ASCII difference
        diff += abs(ord(s) - ord(t))
    return diff  

def mutate_solution(solution):
    ind = random.randint(0, len(solution) - 1)
    solution[ind] = random.choice(string.printable)
    return solution

def SimpleHillClimbing():
    answer = "SARASREE"
    best = generate_random_solution(answer)
    best_score = evaluate(best, answer)
    
    while True:
        print("Score:", best_score, "Solution:", "".join(best))
        
        if best_score == 0:
            print("\nGoal Reached! Final Solution:", "".join(best))
            break
        
        new_solution = mutate_solution(list(best))
        score = evaluate(new_solution, answer)
        
        if score < best_score:
            best = new_solution
            best_score = score

SimpleHillClimbing()
```

<hr>
<h2>Sample Input and Output</h2>
<h2>Sample String:</h2> SARASREE
<h2>Output:</h2>

<img width="492" height="477" alt="Screenshot 2025-10-06 135020" src="https://github.com/user-attachments/assets/b6566b68-e382-4e46-ac06-5acaf3d4b4a3" />

....................................................<br>
..................................................<br>
................................................<br>

<img width="448" height="159" alt="Screenshot 2025-10-06 135051" src="https://github.com/user-attachments/assets/5bf6dc2c-94ac-443d-bdd5-fa858b1054e0" />
<h1>Result:</h1>
Thus the given python program for implement simple hill climbing algorithm was executed successfull.
