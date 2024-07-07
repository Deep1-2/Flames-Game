# Flames-Game
Flames game using Pythion Programing 
def remove_common_characters(name1, name2):
    name1 = name1.lower()
    name2 = name2.lower()
    set1 = set(name1)
    set2 = set(name2)
    common_chars = set1.intersection(set2)
    for char in common_chars:
        name1 = name1.replace(char, '', 1)
        name2 = name2.replace(char, '', 1)
    return name1, name2

def calculate_flames(name1, name2):
    flames = "FLAMES"
    count = len(name1) + len(name2)
    while len(flames) > 1:
        index = (count - 1) % len(flames)
        flames = flames[:index] + flames[index + 1:]
    return flames

def main():
    name1 = input("Enter the first name: ")
    name2 = input("Enter the second name: ")
    name1, name2 = remove_common_characters(name1, name2)
    result = calculate_flames(name1, name2)
    categories = {
        'F': 'Friends',
        'L': 'Love',
        'A': 'Affection',
        'M': 'Marriage',
        'E': 'Enemy',
        'S': 'Siblings'
    }
    print(f"Result: {categories[result]}")

if __name__ == "__main__":
    main()

