#defining function for the whole game
def main():
        import time
        import random
#addinf function for print_pause        
        def print_pause(n,m,o,p):
            print(n,m,o,p)
            time.sleep(3)
#adding play again option            
        def play_again():
            print('game over')
            print('Would you like to play again? (y/n)')  
            x = input('(please enter y or n).')
            while x not in ['y','n']:
                x = input('(please enter y or n).')
            if x=='y':
                main()
            elif x=='n':
                print('thanks for playing the game')
#adding fuctions for scoring                
        def increase_score():
                 total_score=0
                 total_score=total_score+10
                 print_pause('your','score','is',total_score)
        def decrease_score():
            total_score=0
            print_pause('your','score','is',total_score)
            print_pause('you','lost','the','game')
#adding randomness            
        enemy_kinds=['pirate','dragon','fairy','wizard']
        enemy_kind=random.choice(enemy_kinds)
        colors = ['blue', 'green', 'red', 'purple', 'orange']
        wand_color = random.choice(colors)  
        print_pause('You find yourself', 'standing in an open field, filled with grass',
                    'and', 'green wildflowers.')
        print_pause('Rumor has it that a'  , str(enemy_kind)  , 'is somewhere around here',
                    'and has been terrifying the nearby village.')
        print_pause('In front', 'of you', 'is', 'a house.')
        print_pause('To your', 'right', 'is', 'a dark cave.')
        print_pause('In your hand', 'you hold your trusty(but not very effective)',str(wand_color),
                    'magic wand.')        
        def field():
#presenting choices            
            print_pause('Enter 1', 'to', 'knock on', 'the door of the house.')  
            print_pause('Enter 2', 'to', 'peer into', ' the cave.')
            x = input('(please enter 1 or 2).')
            while x not in ['1','2']:
                x = input('(Please enter 1 or 2).')
            if x=='1':
                    def house():
                        print_pause('you knock', 'on the', 'door of', 'the house')
                        print_pause('a',str(enemy_kind),'opens','the door')
                        print_pause('you','realised this is the',str(enemy_kind),'house')
                        print_pause('the',str(enemy_kind),'found','you')
                        print_pause('you think','about','what will','you do')
                        print_pause('enter 1','to cast','a','spell')
                        print_pause('enter 2','to','run','away')
                        x = input('(please enter 1 or 2).')
                        while x not in ['1','2']:
                            x = input('(Please enter 1 or 2).')
                        if x=='1':
                            def spell():
                                print_pause('you','cast','a','spell')
                                print_pause('but your','old magic wand is','weaker than the',str(enemy_kind))
                                print_pause('you have been','turned to','a','cat')
                                decrease_score()
                            spell()
                        elif x=='2':
                              print_pause('you run','back to','the','field')
                              print_pause('you','have not','been','followed')
                              field()
                             
                    house()        
                           
            elif x=='2':
                 print_pause('you','enter','the','cave')
                 print_pause('you find','a','strong and new','magic wand')
                 print_pause('you','take','the new','wand')
                 print_pause('the',str(enemy_kind),'suddenly enters the cave to','attack you')
                 print_pause('you','cast a spell','with the','new wand')
                 print_pause('the spell','kills','the',str(enemy_kind))
                 print_pause('you','are','the','winner')
                 increase_score()
                 print_pause('you','won','this','game')
        field()            
        play_again()
main()    
