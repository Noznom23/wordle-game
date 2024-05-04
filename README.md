   def check_word(hidden_word, guess):
    for i, char in enumerate(guess):
        index_duplicate = []
        count = 0
        for k in range(len(hidden_word)):
            if char == hidden_word[k]:
                index_duplicate.append(k)
        index_guess= []

        for k in range(len(guess)):
            if char == guess[k]:
                index_guess.append(k)
        if i not in index_duplicate:
            count +=1

        if char == hidden_word[i]:
            guess = guess[:i] + char.upper() + guess[i + 1:]
        elif char in hidden_word and i not in index_duplicate and len(index_duplicate)== len(index_guess):
            guess = guess[:i] + '.' + guess[i + 1:]
        elif char in hidden_word and i not in index_duplicate:
            guess = guess[:i] + '.' + guess[i + 1:]
        else:
            guess = guess[:i] + '.' + guess[i + 1:]
    return guess

hidden_word = input()
guess = input()
print(check_word(hidden_word, guess))

