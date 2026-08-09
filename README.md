import pygame
import sys
import time
import os
os.system("color F0")
GREY = '\033[90m'  # ANSI grey for greyed-out shop items
RESET = '\033[30m'

pygame.init()

try:
    # run count
    runs = 0
    highest = 0
    sf = True
    st = 0
    running = True
    font = pygame.font.Font(None, 40)
    codef = pygame.font.Font(None, &)

    def m(pos):
        mx, my = pos
    
        mx = mx * screen.get_width() / real_screen.get_width()
        my = my * screen.get_height() / real_screen.get_height()
    
        return mx, my
    
    def ii(name):
        if hasattr(sys, "_MEIPASS"):
            base = sys._MEIPASS
        else:
            base = os.path.dirname(os.path.abspath(__file__))
    
        return pygame.image.load(
            os.path.join(base, "images", name + ".png")
        ).convert_alpha()

    def db(x, y, width, height, colour=(255, 255, 255), thickness=2, gap=4, border_radius=10):
        pygame.draw.rect(screen, colour,
                         (x, y, width, height),
                         thickness,
                         border_radius=border_radius)
    
        pygame.draw.rect(screen, colour,
                         (x + gap, y + gap, width - gap * 2, height - gap * 2),
                         thickness,
                         border_radius=max(0, border_radius - gap))

    def stt():
        global st
        st = pygame.time.get_ticks()

    def i(image, x, y, width, height, alpha=255):
        scaled_image = pygame.transform.scale(image, (width, height))
        scaled_image.set_alpha(alpha)
        return screen.blit(scaled_image, (x, y))

    def f():
        global event
        global running
        global real_screen  # 讓函數可以更新實際的視窗大小
    
        if event.type == pygame.QUIT:
            running = False
            
        elif event.type == pygame.VIDEORESIZE:
            new_w, new_h = event.w, event.h
            
            # 鎖定 3:2 比例
            if new_w / new_h > 1.5:
                new_w = (new_h * 3) // 2
            else:
                new_h = (new_w * 2) // 3
                
            # 重新設定實際視窗的大小
            real_screen = pygame.display.set_mode((new_w, new_h), pygame.RESIZABLE)
    
    def e():
        # 1. 把你的遊戲畫布（screen）完美縮放到實際視窗（real_screen）的大小
        scaled_game = pygame.transform.scale(screen, real_screen.get_size())
        # 2. 把貼圖畫到實際視窗上
        real_screen.blit(scaled_game, (0, 0))
        # 3. 刷新螢幕
        pygame.display.flip()
        clock.tick(60) 
        

    def ff():
        global event
        global running
        for event in pygame.event.get():
            f()

    def d(x, y, w, h, colour, text):
        rect = pygame.Rect(x, y, w, h)
    
        # Draw the button (supports transparency)
        surface = pygame.Surface((w, h), pygame.SRCALPHA)
        surface.fill(colour)
        screen.blit(surface, (x, y))
    
        # Draw the text
        txt = font.render(text, True, (255, 255, 255))
        screen.blit(txt, txt.get_rect(center=rect.center))
    
        return rect

    def w(text, x, y, colour=(255, 255, 255), fo=font, center=False):
        surface = f.render(str(text), True, colour)
        rect = surface.get_rect()
        if center:
            rect.center = (x, y)
        else:
            rect.topleft = (x, y)
        screen.blit(surface, rect)

    def aprint(text, colour=(255, 255, 255)):
        global event
        global running
    
        line_y = $y
    
        for line in text.split("\n"):
            w(
                line,
                $x,
                line_y,
                colour=colour,
                fo=$font,
                center=$center
            )
            line_y += $line_spacing
        
        pygame.display.update($update_area)
    
        waiting = True
        while waiting and running:
            for event in pygame.event.get():
                f()
    
                if event.type == pygame.KEYDOWN:
                    waiting = False
    
                if event.type == pygame.MOUSEBUTTONDOWN:
                    waiting = False


    def bprint(text, x, y, colour=(255, 255, 255), fo=font, center=False, update_area=None):
        global event
        global running
    
        # draw text
        w(text, x, y, colour, f, center)
    
        # update only selected area, otherwise update whole screen
        if update_area:
            pygame.display.update(update_area)
        else:
            e()
            #pygame.display.update()
    
        # wait for input
        waiting = True
        while waiting and running:
            for event in pygame.event.get():
                f()
    
                if event.type == pygame.KEYDOWN:
                    waiting = False
    
                if event.type == pygame.MOUSEBUTTONDOWN:
                    waiting = False

    def cprint(text, colour=(255, 255, 255)):
        global event
        global running
    
        w(
            text,
            $x,
            $y,
            colour=colour,
            fo=$font,
            center=$center
        )
    
        pygame.display.update([
            $update_area1,
            $update_area2
        ])
    
        waiting = True
        while waiting and running:
            for event in pygame.event.get():
                f()
    
                if event.type == pygame.KEYDOWN:
                    waiting = False
    
                if event.type == pygame.MOUSEBUTTONDOWN:
                    waiting = False
    
    def b():
        i($)
    
    def lb():
        i($)

    def rb():
        i($)

#impoet pics hereoopo



    WIDTH, HEIGHT = 1200, 800 # 你的 3:2 基礎遊戲大小
    real_screen = pygame.display.set_mode((WIDTH, HEIGHT), pygame.RESIZABLE)
    screen = pygame.Surface((WIDTH, HEIGHT)) # 你原本所有的 code 都繼續畫在這裡

    pygame.display.set_caption("Finite Dungeons")
    
    clock = pygame.time.Clock()
    
    running = True
    
    while running:
    
# Finite Dungeons - Demo Version
        # Finite Dungeons
        # Created by Timothy
        # Copyright © 2026 Timothy Tang
        bugs = 0

        
        # To do list:
        #outro
        
        
        #-------------------------------------------------------------------
        # Contents:
        # dictionary, entity, monster and player display, fight, shop, actual buying, main game loop
        #---------------
        

        
        print("Finite Dungeons by Timothy")
        stt()
        while running and pygame.time.get_ticks() - st < 2000:
            i($)
            for event in pygame.event.get():
                f()
            e()
            
            #clock.tick(60)
        print("Copyright © 2026 Timothy Tang")
        
        # -------------------------------
        # INTRODUCTION / BACKSTORY
        # -------------------------------
        def print_intro():
            print("\nWelcome to FINITE DUNGEONS(demo)!")
            print("Long long ago, in the blessed town of...skipping opening cutscene?! How dare you...\nfine, straight to tutorial...")
            print("--- How to play ---")
            print("This is an auto-combat game where life choices and shopping collide, and your aim is to defeat me, the level 30 boss. Why me? Shouldn't have skipped the intro if you want to know😈\nCharacters have 4 stats: HP, ATK DEF and SPD.\nHP is shown in the form hp/max hp, others are shown in the form 'base+extra(total)'\nMonsters gain +1 to every stat each level, while you mainly increase stats by purchasing stuff in the shop before each fight, using a (creative) currency called 'money'.\nThe effect of each item is shown to the right of its name, followed by its price and purchase limit.\nTo purchase an item, simply input its number (found at its left) and enter, repeat if you want multiple purchases.\nAll stat increases refer to base stats unless 'extra' is specified.\nAt the start of runs you can pick (usually) 1 'relics' and 'artefacts', which you will unlock more as your highest level reached increases.\nWhen you get defeated you go back to level 1 and can start a new run, probably with new relics and artefacts you unlocked on the previous run.\n\n\n\n-------combat system------\nFighting in each level consists of 2 main phases: hitting the monster and getting hit by the monster, these two phases loop until the HP of you or the monster reaches 0.\nThe character with higher SPD hits first, if SPD ties, I'll let you hit first, cause I'm genuinely nice.\nWhen getting hit, HP decreases by:\nAttacker total ATK-Defender total DEF (HP lost is at least one if this gives <1)\nThis whole fight is automatic.\nThis is a pretty short game and any% should be easily under 2 mins, with 100% nowhere over 5 mins.\nGood luck, and I shall see you at level 30.\n\n")
        
        #---------❓❓❓❓❓
        #something similar to the dictionary
        #---------
        def vitality_money_penalty(player):
            """Deduct 25% of current money if artefact is Heart of Excessive Vitality."""
            if player.artefact == "vitality" and player.money > 0:
                penalty = player.money * 0.25
                player.money -= penalty
                print(f"Heart of Excessive Vitality drains 25% of your money: -{penalty:.2f} Money")
                print("Apparently, being super healthy is expensive — your wallet got a protein shake tax!")
        
        #achievements
        
        ac = {
            "pic_kill": False,
            "negative_money": False,
            "shop_death": False,
            "one_shot": False,
            "trun": False,
            "okill": False,
            "drich": False,
            "hmode": False
        }
        
        def save():
            alphabet = "0123456789ABCDEFGHJKLMNIPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz"
        
            # ---------- Pack achievements into 8 bits ----------
            achievement_bits = (
                (1 if ac["pic_kill"] else 0) << 7 |
                (1 if ac["negative_money"] else 0) << 6 |
                (1 if ac["shop_death"] else 0) << 5 |
                (1 if ac["one_shot"] else 0) << 4 |
                (1 if ac["trun"] else 0) << 3 |
                (1 if ac["okill"] else 0) << 2 |
                (1 if ac["drich"] else 0) << 1 |
                (1 if ac["hmode"] else 0)
            )
        
            # ---------- Pack everything into one integer ----------
            value = runs
            value = (value << 5) | highest
            value = (value << 8) | achievement_bits
        
            # ---------- Convert to Base 61 ----------
            if value == 0:
                code = alphabet[0]
            else:
                code = ""
                while value > 0:
                    code = alphabet[value % 61] + code
                    value //= 61
        
            # Always 5 characters long
            code = code.rjust(5, alphabet[0])
        
            return code
        
        def hpb():
            player.hp = min(player.hp, player.max_hp)
        
        def get_atk(entity):
            return entity.atk + entity.extra_atk
        
        
        def get_df(entity):
            return entity.df + entity.extra_df
        
        
        def get_spd(entity):
            return entity.spd + entity.extra_spd
        
        
        def get_max_hp(entity):
            return entity.max_hp + entity.extra_max_hp
        
        forbidden_messages = [
            "You wrote out the formula to beat this game (a wrong one), the monster dies laughing!",
            "You wrote out Navier-Stokes equation, the monster dies trying to understand!",
            "You wrote out Einstein’s field equations, the monster dies overwhelmed!",
            "You wrote out Schrodinger's equation, the monster dies in confusion!",
            "You scribbled down Maxwell's equations, the monster dies from panic!",
            "You wrote out Rocket propulsion formulas, the monster dies screaming!",
            "You jotted down Euler's formula, the monster dies in horror!",
            "You wrote out the cubic formula, the monster faints and dies!",
            "You scribbled out the Pythagorean theorem, the monster dies of fright!",
            "You wrote out the equation for the area of a triangle, the monster got scared to death!"
        ]
        
        
        # Relic names rn😎😎
        relic_names = {
            "family": "Picture of Family",
            "blessed": "Blessed Emblem",
            "forbidden": "Forbidden Book",
            "bk": "K*C bronze membership card",
            "e-sword": "Automatic Counter E-Sword",
            "yd": "RAY-24 Drone",
            "sk": "K*C silver membership card",
            "meowton": "Meowton’s Second Lawsuit",
            "gk": "K*C gold membership card",
            "dk": "K*C diamond membership card"
        }
        print_intro()
        
        
        # -------------------------------
        # DESCRIPTIONS (505 input)
        # -------------------------------
        
        relic_descriptions = {
            "family": "Picture of Family — Revives once to 1 HP when defeated.",
            "blessed": "Blessed Emblem — Every 3 monsters defeated, +5 max HP and heal max. -1 HP when run starts",
            "forbidden": "Forbidden Book — unlocks in shop: ink - costs 7, max purchase 10, max hold 1, auto consumed at start of fight and defeats the monster.",
            "bk": "K*C bronze membership card - chicken heals 2 more hp",
            "yd": "RAY-24 Drone - have a drone to help you fight! Buy up to 6 upgrades",
            "e-sword": "E-Sword — Starts with +1 ATK.",
            "sk": "K*C silver membership card - chickens heal 2 more hp, max purchase +2",
            "meowton": "Meowton's 2nd lawsuit — -1 DEF when equipping, gain extra ATK = total SPD",
            "gk": "K*C gold membership card - chickens heal max, no max purchase limit",
            "dk": "K*C diamond membership card - chickens heal max, remove all conditions required to purchase chickens"
        }
        
        artefact_descriptions = {
           # "discount": "Discount Ticket — Buy one equipment, get the other two free.",
            "devotion": "The Damned Proof of Devotion - Elixir unlocked in shop - costs 1, max hp - [elixir bought], SPD-1, extra spd+6, for next 3 fights -2 extra SPD after fight, can only buy one per turn.",
            "socks": "Cursed Socks — Boots sealed. When HP <= 3, unlocks option in shop to decrease and seal max HP to current HP, gaining the same amount of ATK.",
            "coinpot": "Alchemist's Coinpot — Every 3 money left before fight gives 2 money.",
            "ar": "Abyssal Rad-Blood Oath - Unlocks a shop option once per run to lose 5 max HP, gain money={level beaten/5 (round down)}³.",
            "carrier": "Carrier of Legend — Choose 3 relics, switch from the 1st to 2nd to 3rd one. All stats except max hp drains to 1 at relic switch.",
            "vitality": "Heart of Excessive Vitality — Start with 50 HP but lose 25% money before fights, at the start of fights, lose HP equal to money/2."
        }
        
        # removed shop des as already there
        # shop_descriptions = {
           # "sword": "Sword — +1 ATK.",
         #   "battery": "Battery — Adds counter attacks for E-Sword.",
          #  "shield": "Shield — +1 DEF.",
           # "boots": "Boots — +1 SPD.",
            #"chicken": "Chicken — +5 HP if missing enough health.",
          #  "book_atk": "Book of Attack — Double ATK.",
           # "book_def": "Book of Defence — Double DEF.",
            #"book_hp": "Book of Max HP — Double max HP after next fight.",
           # "book_spd": "Book of Speed — Double SPD.",
           # "book_heal": "Book of Healing — Full heal.",
         #   "ink": "Forbidden Ink — Insta-kill next monster when entering fight.",
          #  "elixir": "Elixir — +5 HP, -5 max HP."
        # }
        
        def print_relic_descriptions(unlocked_relics):
            print("\n--- RELIC DESCRIPTIONS ---")
            for r in unlocked_relics:
                print(f"{relic_descriptions.get(r, 'No description.')}")
            input("\nPress Enter to return...")
        
        
        def print_artefact_descriptions(unlocked_artefacts):
            print("\n--- ARTEFACT DESCRIPTIONS ---")
            for a in unlocked_artefacts:
                print(f"{artefact_descriptions.get(a, 'No description.')}")
            input("\nPress Enter to return...")
        
        
        #def print_shop_descriptions(player):
            #print("\n--- SHOP ITEM DESCRIPTIONS ---")
            #for key in shop_descriptions:
                #print(f"{shop_descriptions[key]}")
            #input("\nPress Enter to return to shop...")
        
        
        # -------------------------------
        # ENTITY CLASSES
        # -------------------------------
        class Entity:
            """Base class for player and monsters."""
            def __init__(self, hp, atk, df, spd):
                self.max_hp = hp
                self.hp = hp
        
                self.atk = atk
                self.extra_atk = 0
        
                self.df = df
                self.extra_df = 0
        
                self.spd = spd
                self.extra_spd = 0
        
                self.extra_max_hp = 0
        
            def is_alive(self):
                return self.hp > 0
        
        
        class Player(Entity): #sself
            """Player class with relics, artefacts, counters, money, and book tracking."""
            def __init__(self, relic, artefact):
                super().__init__(10, 1, 1, 1)
                self.money = 0
                self.used_e_sword_before = 0
                self.artefact = artefact
                # Carrier of Legend support
                if artefact == "carrier":
                    self.relics = relic  # relic parameter is a list of 3 chosen relics
                    self.active_relic_index = 0
                    self.relic = self.relics[self.active_relic_index]  # Only first is active
                else:
                    self.relic = relic
        
                self.revive_used = False   # Picture of Family
                self.forbidden_ink = 0     # Forbidden Book effect
                self.forbidden_ink_total = 0 
                self.counters = 0          # Battery / E-Sword effect
                self.coinpot_bonus = 0     # Alchemist's Coinpot effect
                self.c = 0
                self.cc = 0
                self.ccc = 0
                self.bought_elixir_this_turn = 0
                # Books (per-run limit)
                self.books = {"atk":0,"def":0,"hp":0,"spd":0,"heal":0}
                # Shop purchase tracking (per-run limits)
                self.bought = {"sword":0,"shield":0,"boots":0,"chicken":0,"battery":0,"elixir":0}
                self.rm = True #only False after message prints
                if self.relic == "meowton":
                    self.extra_atk += self.spd
                self.socks_sealed = False
                self.pending_hp_multiplier = 1
                self.osp = False
                self.not_ar = True
                self.ppa = False
                self.switch = 0
                self.ydatk = 0
                self.yd1 = 0
                self.yd2 = 0
                self.yd3 = 0
                self.yd4 = 0
                self.ydus = 0
                self.died = False
                
        
        # -------------------------------
        # MONSTER CREATION
        # -------------------------------
        def create_monster(level):
            """Create monster stats based on level."""
            return Entity(4 + level, level, level, level)
        
        
        # -------------------------------
        # FIGHT MECHANICS
        # -------------------------------
        def attack(attacker, defender):
            global sf
            atk = get_atk(attacker)
            df = get_df(defender)
        
            dmg = atk - df if atk > df else 1
            defender.hp -= dmg
        
            if isinstance(attacker, Player):
                if sf == True:
                    print(f"\nYou deal {dmg} dmg!")
                    print(f"Your HP: {attacker.hp}       Monster's HP: {defender.hp + dmg}-{dmg}={defender.hp}")
            else:
                if sf == True:
                    print(f"\nMonster deals {dmg} dmg!")
                    print(f"Your HP: {defender.hp + dmg}-{dmg}={defender.hp}       Monster's HP: {attacker.hp}")
            if isinstance(defender, Player):
                if defender.hp <= 0 and defender.relic == "family" and not defender.revive_used:
                    defender.hp = 1
                    defender.revive_used = True
                    print("Harshly, you are shuffled to the ground. Out of your pocket a picture flew out, the picture that stands as your fuel, the picture that supported you up to here, the picture that captures the moment you can never return to...\nthen TRASH\nnot dramatically, not emotionally, the monster trampled on it.\nYou feel a string snapped inside you as the picture shattered into pieces.\nBefore you knew it, you were charging towards the monster with all your might...")
        
        def get_atk(entity):
            return entity.atk + entity.extra_atk
        
        
        def get_df(entity):
            return entity.df + entity.extra_df
        
        
        def get_spd(entity):
            return entity.spd + entity.extra_spd
        
        
        def get_max_hp(entity):
            return entity.max_hp + entity.extra_max_hp
        
        
        #🤺🤺🤺🤺🤺🧯🧯🧯🧯🧯
        def fight(player, monster):
            
            global level, event
            """Simulate fight until player or monster dies."""
        
            if player.yd2 == 1:
                dmg = max(player.ydatk - monster.df, 1)
            if player.yd2 == 2:
                dmg = max(player.ydatk*2 - monster.df, 1)
            if player.yd2 == 3:
                dmg = max(player.ydatk*2 - max(0, monster.df-player.ydatk*2), 1)
            if player.yd2 == 4:
                dmg = max(player.ydatk*2 - max(0, monster.df-player.ydatk*2), 1)
                print(f"RAY-24 fires a Tomahawk Cruise Missile at the monster!\nmonster hp: {monster.hp}-{dmg}={monster.hp-dmg}    monster def: {monster.df}-{dmg*2}={max(0, monster.df-dmg*2)}(minimum 0)")
                monster.hp -= dmg
                monster.df -= dmg*2
                monster.df = max(monster.df, 0)
                dmg = max(player.ydatk*2 - max(0, monster.df-player.ydatk*2), 1)
                print(f"RAY-24 fires a second Tomahawk Cruise Missile at the monster!\nmonster hp: {monster.hp}-{dmg}={monster.hp-dmg}    monster def: {monster.df}-{dmg*2}={max(0, monster.df-dmg*2)}(minimum 0)")
                monster.hp -= dmg
                monster.df -= dmg*2
                monster.df = max(monster.df, 0)
                if monster.hp <= 0:
                    ac["okill"] = True
                    print("Stop wasting ammo on dead bodies!")
                dmg = max(player.ydatk*2 - max(0, monster.df-player.ydatk*2), 1)
                print(f"RAY-24 fires a third Tomahawk Cruise Missile at the monster!\nmonster hp: {monster.hp}-{dmg}={monster.hp-dmg}    monster def: {monster.df}-{dmg*2}={max(0, monster.df-dmg*2)}(minimum 0)")
                monster.hp -= dmg
                monster.df -= dmg*2
                monster.df = max(monster.df, 0)
            if player.yd2 >= 1 and player.yd2 <4:
                print(f"RAY-24 fires a Tomahawk Cruise Missile at the monster!\nmonster hp: {monster.hp}-{dmg}={monster.hp-dmg}")
                monster.hp -= dmg
        
            if player.ppa == True:
                player.hp -= player.money//2
                player.hp = min(player.hp, player.max_hp)
                player.ppa = False
                print(f"weight of your wallet is draining your health, hp-{player.money//2}")
            #ink
            if player.hp > 0 and player.forbidden_ink > 0:
                # Determine which message to show
                ink_used = 10 - player.forbidden_ink_total  # 0-indexed
                if ink_used >= len(forbidden_messages):
                    ink_used = len(forbidden_messages) - 1
                if level != 30:
                    print(forbidden_messages[ink_used])
                else:
                    print("Beat game special text not avalible in demo version")
                monster.hp = 0
                player.forbidden_ink -= 1
                return True
        
        
            while player.is_alive() and monster.is_alive():
                # Determine turn order
                if get_spd(player) >= get_spd(monster):
                    attack(player, monster)
                    if not monster.is_alive():
                        break
                    if not player.is_alive():
                        break
                    if monster.is_alive():
                        if player.counters > 0:
                            player.counters -= 1
                            attack(player, monster)
                            if not monster.is_alive():
                                break
                            if not player.is_alive():
                                break
                        else:
                            attack(monster, player)
                            if not monster.is_alive():
                                break
                            if not player.is_alive():
                                break
        
                else:
                    if player.counters > 0:
                        player.counters -= 1
                        attack(player, monster)
                        if not monster.is_alive():
                            break
                        if not player.is_alive():
                            break
                    else:
                        attack(monster, player)
                        if not monster.is_alive():
                            break
                        if not player.is_alive():
                            break
                    if monster.is_alive():
                        attack(player, monster)
                        if not monster.is_alive():
                            break
                        if not player.is_alive():
                            break
        
                # Picture of Family activation
                if player.hp <= 0 and player.relic == "family" and not player.revive_used:
                    #player.hp = 1
                    #player.revive_used = True
                    #print("Harshly, you are shuffled to the ground. Out of your pocket a picture flew out, the picture that stands as your fuel, the picture that supported you up to here, the picture that captures the moment you can never return to...\nthen TRASH\nnot dramatically, not emotionally, the monster trampled on it.\nYou feel a string snapped inside you as the picture shattered into pieces.\nBefore you knew it, you were charging towards the monster with all your might...")
                    if get_atk(player) <= monster.df:
                        if monster.hp <= 1:
                            print("From that burst of energy not explainable by science, you regained just enough power to put the down the monster before dropping to the ground\nAfter what felt like eternities later, you dragged yourself up, and moved on, just like what they would have wanted to see...")
                            ac["pic_kill"] = True #for achievement system adding later
                    elif get_atk(player) >= monster.df+monster.hp:
                        print("From that burst of energy not explainable by science, you regained just enough power to put the down the monster before dropping to the ground\nAfter what felt like eternities later, you dragged yourself up, and moved on, just like what they would have wanted to see...")
                        ac["pic_kill"] = True #for achievement system adding later
        
        
            return player.is_alive()
        
        
        # -------------------------------
        # DISPLAY PLAYER + NEXT MONSTER
        # -------------------------------
        def display_player_and_next_monster(player, level):
            """Show current player stats and next monster stats."""
        
        
            print("\n--- Player Stats ---")
            print(f"HP: {player.hp}/{player.max_hp}")
            print(f"ATK: {player.atk}", end="")
            if player.extra_atk > 0:
                print(f"+{player.extra_atk} ({get_atk(player)})")
            else:
                print()
        
            print(f"DEF: {player.df}", end="")
            if player.extra_df > 0:
                print(f"+{player.extra_df} ({get_df(player)})")
            else:
                print()
        
            print(f"SPD: {player.spd}", end="")
            if player.extra_spd > 0:
                print(f"+{player.extra_spd} ({get_spd(player)})")
            else:
                print()
            if player.relic == "family" and player.revive_used == False:
                print("Revives: 1")
                
            if player.counters > 0:
                print(f"Counters: {player.counters}")
        
            m = create_monster(level)
            print(f"\nNext Monster - Level {level}")
            print(f"HP: {m.hp}")
            print(f"ATK: {m.atk}")
            print(f"DEF: {m.df}")
            print(f"SPD: {m.spd}")
        
        
        # -------------------------------
        # SHOP MECHANICS
        # -------------------------------

        
        # -------------------------------
        # main menu stuff and...
        # ...MAIN GAME LOOP
        # -------------------------------
        
        def pa ():
        
            print("---unlocked achievements---")
        
            if ac["trun"] == True:
                print("The real game")
                print(GREY + "beat level 30 in 3 runs\n" + RESET)
        
            if ac["drich"] == True:
                print("you can't take it with you")
                print(GREY + "die with over 25m money\n" + RESET)
        
            if ac["one_shot"] == True:
                print("雑魚")
                print(GREY + "one shot a monster\n" + RESET)
        
            if ac["okill"] == True:
                print("'just in case its still alive, you know?'")
                print(GREY + "shoot a [thing] at a dead monster\n" + RESET)
        
            if ac["hmode"] == True:
                print("hard mode")
                print(GREY + "inevitably die on level 2\n" + RESET)
        
        
            if ac["negative_money"] == True:
                print("Well, you did say ALL conditions")
                print(GREY + "purchase a chicken without enough money\n" + RESET)
            
            if ac["shop_death"] == True:
                print("as dangerous as 'monster'")
                print(GREY + "die in shop\n" + RESET)
            
            if ac["pic_kill"] == True:
                print("one hp actually helps?!")
                print(GREY + "kill a monster after reviving\n" + RESET)
                    
            print("---locked achievements---")
        
            if ac["trun"] == False:
                print("The real game")
                print(GREY + "beat level 30 in 3 runs\n" + RESET)
        
            if ac["drich"] == False:
                print("you can't take it with you")
                print(GREY + "die with over 25m money\n" + RESET)
        
            if ac["one_shot"] == False:
                print("雑魚")
                print(GREY + "one shot a monster\n" + RESET)
        
            if ac["okill"] == False:
                print("'just in case its still alive, you know?'")
                print(GREY + "shoot a [thing] at a dead monster\n" + RESET)
        
            if ac["hmode"] == False:
                print("hard mode")
                print(GREY + "inevitably die on level 2\n" + RESET)
        
        
            if ac["negative_money"] == False:
                print("Well, you did say ALL conditions")
                print(GREY + "?????????\n" + RESET)
            
            if ac["shop_death"] == False:
                print("as dangerous as 'monster'")
                print(GREY + "die in shop\n" + RESET)
            
            if ac["pic_kill"] == False:
                print("one hp actually helps?!")
                print(GREY + "kill a monster after reviving\n" + RESET)
        
        
        def pl():
            print("\n---relics---")
            print("Picture of Family \nRevives once to 1 HP when defeated.")
            print(GREY + "'If you don't believe in yourself, believe in me who believe in you'\n" + RESET)
            
            print("Blessed Emblem \nEvery 3 monsters defeated, +5 max HP and fully heals. hp-1 when run starts")
            print(GREY + "This Emblem is really blessed, definitely, trust.\n" + RESET)
            
            print("Forbidden Book \nUnlocks in the shop: ink-costs 7, max purchase 10, max hold 1, automatically consumed at start of fight and defeats the monster.")
            print(GREY + "What can be more cursed than a book full of equations?\n" + RESET)
            
            print("K*C bronze membership card " + GREY + "(unlocks after beating lv. 4)" + RESET + " \nChickens heal 2 more HP")
            print(GREY + "A membership card that gets you extra food on order!\n" + RESET)
            
            print("K*C silver membership card " + GREY + "(unlocks after beating lv. 10)" + RESET + " \nChickens heal 2 more HP, max purchase +2")
            print(GREY + "Don't ask how a membership card increases stock, it's what you call a 'Fantasy world'\n" + RESET)
        
            print("RAY-24 Drone" + GREY + "(unlocks after beating lv. 7)" + RESET + " \nHave a drone to help you fight, having extra atk=its atk! Buy up to 6 accumulative upgrades")
            print(GREY + "This relic is made in respect to my friend who managed to looked through this unimaginable messy code and spent a few hours given me insights\n" + RESET)
                
            print("Meowton's 2nd lawsuit " + GREY + "(unlocks after beating lv. 15)" + RESET + " \n-1 DEF upon equipping, gain extra ATK = total SPD")
            print(GREY + "I know Newton's 2nd law is multiply, but I need to consider game balance ok?\n" + RESET)
            
            print("K*C gold membership card " + GREY + "(unlocks after beating lv. 20)" + RESET + " \nChickens heal max, no max purchase limit")
            print(GREY + "Shouldn't infinite K*C chicken damage your health? Anyways, eating ALWAYS heals...\n" + RESET)
            
            if highest < 30:
                print("????????" + GREY + "(unlocks after beating lv. 30)" + RESET + " \n???????????\n")
            else:
                print("K*C diamond membership card " + GREY + "(unlocks after beating lv. 30)" + RESET + " \nChickens heal max, remove all conditions required to purchase chickens\n")
                print(GREY + "Sorry for the 'yet another K*C card' disappointment, I am not a very creative person" + RESET)
        
            print("---artefacts--")
            print("The Damned Proof of Devotion " + GREY + "(unlocks after beating lv. 3)" + RESET + " \nElixir unlocked in shop: costs 1, max HP - [elixir bought], SPD-1, extra SPD+6; for next 3 fights, -2 extra SPD after fight, can only buy one per turn.")
            print(GREY + "But to some soul, isn't energy drinks their only 'elixir'?\n" + RESET)
            
            print("Cursed Socks " + GREY + "(unlocks after beating lv. 6)" + RESET + " \nBoots sealed. When HP <= 3, unlocks option in the shop to decrease and seal max HP to current HP, gaining the same amount of ATK.")
            print(GREY + "Socks in certain conditions can really have a high ATK, don't find it out the hard way...\n" + RESET)
            
            print("Alchemist's Coinpot " + GREY + "(unlocks after beating lv. 8)" + RESET + " \nEvery 3 money left before fight gives 2 money.")
            print(GREY + "So...do the monsters transfer money to you digitally when they get defeated?\n" + RESET)
            
            print("Abyssal Rad-Blood Oath " + GREY + "(unlocks after beating lv. 17)" + RESET + " \nUnlocks a shop option once per run to lose 5 max HP, gain money = {level beaten/5 (round down)}³.")
            print(GREY + "A contract to test suspicious water samples in the dungeon, a world without power oppression wouldn't be a realistic one, would it?\n" + RESET)
            
            print("Heart of Excessive Vitality " + GREY + "(unlocks after beating lv. 20)" + RESET + " \nStart with 50 HP but lose 25% money before fights, at start of fight HP - money/2.")
            print(GREY + "I hope that is the right use of 'vitality', I don't fully understand that word till this day\n" + RESET)
            
            print("Carrier of Legend " + GREY + "(unlocks after beating lv. 20)" + RESET + " \nChoose 3 relics, switch from the 1st to 2nd to 3rd one. All stats except max HP drain to 1 at relic switch.")
            print(GREY + "The biggest relic is a drone, so the volume of this bag is realistic...I hope?\n" + RESET)
            
        
        
        def pc():qqwq
            print("\nGuido van Rossum, creator of Python, who provided coding language to me")
            
            print("\nSteve Jobs, co-founder of Apple, who provided my device to me")
            
            print("\nNick Holonyak Jr., inventor of the practical LED, who provided glowing screens to me")
            
            print("\nOleg Losev, LED research pioneer, who provided more glowing things to type on to me")
            
            print("\nAlessandro Volta, inventor of the battery, who provided portable power to me")
            
            print("\nMichael Faraday, discoverer of electromagnetic induction, who provided electricity generation to me")
            
            print("\nTim Berners-Lee, creator of the World Wide Web, who provided internet access to me for reserches")
            
            print("\nLarry Page and Sergey Brin, founders of Google, who provided more searching ability to me")
            
            print("\nLinus Torvalds, creator of Linux, who provided computing foundations to me")
            
            print("\nDennis Ritchie, creator of C language, who provided programming foundations to me")
            
            print("\nThe inventors of WiFi, who provided freedom(wireless connection) to me")
            
            print("\nThe inventors of electricity, who provided energy to me(literally and metaphorically)")
            
            print("\nThe inventor of the chair, who provided comfort to me while coding")
            
            print("\n---special credits---")
        
            print("pianoplayer1224, who distracted me from making this game by giving me a code to solve, and by giving me a game of theirs to play, and by saying 'He wasn't impressed' at this very moment I am typing. But more importantly, for their contributions to my knowledge of coding and contributions to all angles of this game as the first playtester.")
            
            print("\nRachmaninov and blackpenredpen, who provided me with emotional support by writing a 2nd piano concerto and made YouTube videos respectively. (Check out Rach 2 and blackpenredpen if you don't know them!!)")
            
            print("\nMy family, who provided me with love, shelter, and most importantly, food, when I am making this game")
            
            print("\nAll my friends who played the paper version of this game, contributing huge to the balancing and shaping of this game")
            
            print("\nAnd of course, YOU, the player, who decided to read the credits instead of playing the game, proving to me how my game is not even as entertaining as some random credits, providing me with emotional damage\n")
        
        def load(code):
            global runs, highest, ac, st, running, event
        
            alphabet = "0123456789ABCDEFGHJKLMNIPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz"
        
            # ---------- Basic validation ----------
            if len(code) != 5:
                print("Invalid save code.")
                stt()
                while running and pygame.time.get_ticks()-st <= 2000:
                    ff()
                    screen.fill((0, 0, 0)) 
                    w($)
                    e()
                    #pygame.display.update() 
                  #  clock.tick(60)
                return False
        
            # ---------- Convert Base 61 back to integer ----------
            value = 0
            for char in code:
                if char not in alphabet:
                    stt()
                    while running and pygame.time.get_ticks()-st <= 2000:
                        #print("Invalid save code.")
                        ff()
                        screen.fill((0, 0, 0)) 
                        w($)
                        e()
                        #pygame.display.update() 
                        #clock.tick(60)
                    return False
                value = value * 61 + alphabet.index(char)
        
            # ---------- Unpack ----------
            achievement_bits = value & 0xFF
            value >>= 8
        
            highest = value & 0b11111
            value >>= 5
        
            runs = value
        
            # ---------- Range checking ----------
            if runs > 1024 or highest > 30:
                #print("Corrupted save code.")
                stt()
                while running and pygame.time.get_ticks()-st <= 2000:
                        
                    ff()
                    screen.fill((0, 0, 0)) 
                    w($)
                    e()
                    #pygame.display.update() 
                    #clock.tick(60)
                return False
                return False
        
            # ---------- Decode achievements ----------
            ac["pic_kill"]       = bool((achievement_bits >> 7) & 1)
            ac["negative_money"] = bool((achievement_bits >> 6) & 1)
            ac["shop_death"]     = bool((achievement_bits >> 5) & 1)
            ac["one_shot"]       = bool((achievement_bits >> 4) & 1)
            ac["trun"]           = bool((achievement_bits >> 3) & 1)
            ac["okill"]          = bool((achievement_bits >> 2) & 1)
            ac["drich"]          = bool((achievement_bits >> 1) & 1)
            ac["hmode"]          = bool(achievement_bits & 1)
        
            print(f"\nSave loaded successfully.\nRuns: {runs}   Highest lv. beaten: {highest}\n")
            stt()
            while running and pygame.time.get_ticks()-st <= 2000:
                #print("Invalid save code.")
                ff()
                screen.fill((0, 0, 0)) 
                w($)
                e()
                #pygame.display.update() 
                #clock.tick(60)
            
            return True
        
        def run():
            global runs, running, event
            global level
            global highest
            died_run = False
            unlocked_relics = [
                "family",
                "blessed",
                "forbidden"
            ]
            all_artefacts = {
                "devotion": 3,
                "socks": 6,
                "coinpot": 8,
                "ar": 17,
                "carrier": 20,
                "vitality": 20
            }
            while running: #rubqqwq
                if died_run:
                    break
                # E-Sword not put in game untill balanced
                if highest >= 99999 and "e-sword" not in unlocked_relics:
                    unlocked_relics.append("e-sword")
        
                if highest >= 4 and "bk" not in unlocked_relics:
                    unlocked_relics.append("bk")
        
                if highest >= 7 and "sk" not in unlocked_relics:
                    unlocked_relics.append("sk")
                
                if highest >= 10 and "yd" not in unlocked_relics:
                    unlocked_relics.append("yd")
        
                if highest >= 12 and "gk" not in unlocked_relics:
                    unlocked_relics.append("gk")
        
                if highest >= 15 and "meowton" not in unlocked_relics:
                    unlocked_relics.append("meowton")
        
                if highest >= 30 and "dk" not in unlocked_relics:
                    unlocked_relics.append("dk")
        
                # Update artefacts every run ffgf
                unlocked_artefacts = [a for a, lvl in all_artefacts.items() if highest >= lvl]
                runs += 1
                # Choose artefact first
                if not unlocked_artefacts:
                    print("No artefacts unlocked yet! You must continue without one.")
                    artefact = None
                else:
                    while True:
                        print("\nChoose, with all your brain power, one artefact:")
                        print("0 No artefact")
                        artefact_names = {
                            #"discount": "Shopping Discount Ticket",
                            "devotion": "The Damned Proof of Devotion (i.e. corner shop loyalty card)",
                            "socks": "Cursed (old, smelly) Socks",
                            "coinpot": "Alchemist's Coinpot (savings account)",
                            "ar": "Abyssal Rad-Blood Oath (suspicious nuclear food testing contract)",
                            "carrier": "The carrier of legends (Backpack)",
                            "vitality": "Heart of Excessive Vitality (Protein shake heath package plan)"
                        }
            
                        for i, a in enumerate(unlocked_artefacts, 1):
                            print(f"{i} {artefact_names[a]}")
                        print("505 show artefact descriptions")
        
                        try:
                            artefact_choice = int(input("> "))
                            if artefact_choice == 0:
                                artefact = None
                                break
                            if 1 <= artefact_choice <= len(unlocked_artefacts):
                                artefact = unlocked_artefacts[artefact_choice - 1]
                                break
                            elif artefact_choice == 505:
                                print_artefact_descriptions(unlocked_artefacts)
        
                                continue
                            else:
                                print("Invalid choice. Select a valid artefact number.")
                        except ValueError:
                            print("Invalid input. Please enter a number.")
        
        
                # Choose relic
                # Choose relic(s)
                print("\nChoose, very carefully, your relic:")
        
                # If Carrier of Legend, pick 3 relics
                if artefact == "carrier":
        
                        while True:
                        #while True:
                            print("You chose the Carrier of Legend! Pick 3 relics in order (only the first one is active at start).")
                            player_relics = []
                        
                            for n in range(1, 4):
                                while True:
                                    print(f"\nSelect relic #{n}:")
                                    for i, r in enumerate(unlocked_relics, 1):
                                        print(f"{i} {relic_names[r]}")
                                    print("505 show relic descriptions")
                        
                                    try:
                                        relic_choice = input("> ")
                        
                                        if relic_choice == "505":
                                            print_relic_descriptions(unlocked_relics)
                                            continue    # goes back to selecting the SAME relic number
                        
                                        relic_choice = int(relic_choice)
                        
                                        if 1 <= relic_choice <= len(unlocked_relics):
                                            chosen = unlocked_relics[relic_choice - 1]
                        
                                            if chosen in player_relics:
                                                print("You already picked that relic.")
                                                continue
                        
                                            player_relics.append(chosen)
                                            break       # finished choosing this relic
                        
                                        print("Invalid choice.")
                        
                                    except ValueError:
                                        print("Invalid input.")
                        
                            break    # all 3 relics have been chosen
                else:
                    # Normal single relic pick
                    while True:
                        print("0 No relic")
                        for i, r in enumerate(unlocked_relics, 1):
                            print(f"{i} {relic_names[r]}")
                        print("505 show relics description")
        
                        try:
                            relic_choice = int(input("> "))
                            if relic_choice == 0:
                                relic = None
                                break
                            if relic_choice == 505:
                                print_relic_descriptions(unlocked_relics)
                                continue
                            if 1 <= relic_choice <= len(unlocked_relics):
                                relic = unlocked_relics[relic_choice - 1]
                                break
                            else:
                                print("Invalid choice. Select a valid relic number.")
                        except ValueError:
                            print("Invalid input. Please enter a number.")
        
                # create player
                if artefact == "carrier":
                    player = Player(player_relics, artefact)
                else:
                    player = Player(relic, artefact)
        
        
                # E-Sword start-of-run bonus
                if artefact == "carrier":
                    # only the first active relic gives the bonus
                    if player.relics[0] == "e-sword":
                        player.atk += 1
                        print("You have your own sword, not needing the shop one! +1 ATK!")
                else:
                    if player.relic == "e-sword":
                        player.atk += 1
                        print("You have your own sword, not needing the shop one! +1 ATK!")
        
                # Heart of Excessive Vitality effect
                if artefact == "vitality":
                    player.max_hp = 50
                    player.hp = 50
        
                if player.relic == "meowton":
                    player.df -= 1
                    print("A law suit is not one that provides defence ability, DEF-1")
        
                if artefact == "carrier":
            # Check all 3 relics for Blessed Emblem
                    if "blessed" in player.relics:
                        player.hp -= 1
                        print("You fumble with the Blessed Emblem while getting ready and pinched yourself, losing 1 HP.....\nI am not laughing at you, I promise.")
                else:
                    if player.relic == "blessed":
                        player.hp -= 1
                        print("You fumble with the Blessed Emblem while getting ready and pinched yourself, losing 1 HP.....\nI am not laughing at you, I promise.")
        
                c = player.c
                cc = player.cc
                ccc = player.ccc
                bought_elixir_this_turn = player.bought_elixir_this_turn
        
                # Fight/shop loop ffgf
                for level in range(1, 31):
                    if player.osp == True:
                        print("'雑魚(pointless peasant)', you smirked")
                        ac["one_shot"] = True
                
                    if player.revive_used == True:
                        if player.rm == True:
                            print("From that burst of energy not explainable by science, you regained just enough power to put the down the monster before dropping to the ground\nAfter what felt like eternities later, you dragged yourself up, and moved on, just like what they would have wanted to see...")
                            ac["pic_kill"] = True #for achievement system adding later
                            player.rm = False
                # Apply pending Book of Max HP effect
                    if player.pending_hp_multiplier > 1:
                        player.max_hp = int(player.max_hp * player.pending_hp_multiplier)
                        print(f"Book of Max HP activates! Your max HP is now {player.max_hp}.")
                        player.pending_hp_multiplier = 1
        
        
        
        
                    # Rewards and Blessed Emblem and cans
                    player.money += 4
                    if player.yd4 >= 1:
                        player.money += player.ydatk
                    if player.yd4 >= 2:
                        player.money += 6
                    if player.yd4 >= 3:
                        player.money += 12
                    if player.yd4 >= 4:
                        player.money += player.ydatk
                        player.money += 22
                    if player.yd3 >= 1:
                        player.hp += 5
                        player.hp = min(player.hp, player.max_hp)
                    if player.yd3 >= 2:
                        player.hp += 10
                        player.hp = min(player.hp, player.max_hp)
                    if player.yd3 >= 3:
                        player.hp += 25
                        player.hp = min(player.hp, player.max_hp)
                    if player.yd3 >= 4:
                        player.hp += 40
                        player.hp = min(player.hp, player.max_hp)
        
                    if player.relic == "blessed" and level % 3 == 0:
                        if not player.socks_sealed:
                            player.max_hp += 5
                        player.hp = player.max_hp
        
                    if player.c != 0:
                        player.c -= 1
                        if player.relic == "meowton":
                            player.extra_atk -= player.extra_spd
                        player.extra_spd -= 2 
                        if player.relic == "meowton":
                            player.extra_atk += player.extra_spd
                    if player.cc != 0:
                        player.cc -= 1
                        if player.relic == "meowton":
                            player.extra_atk -= player.extra_spd
                        player.extra_spd -= 2 
                        if player.relic == "meowton":
                            player.extra_atk += player.extra_spd
                    if player.ccc != 0:
                        player.ccc -= 1
                        if player.relic == "meowton":
                            player.extra_atk -= player.extra_spd
                        player.extra_spd -= 2 
                        if player.relic == "meowton":
                            player.extra_atk += player.extra_spd
        
        
                    # Shop → 0 input starts fight
                    
                    result = shop(player, level)
                    if result == "dead":
                        highest = max(highest, level-1)
                        print(f"\nYou died! Level completed this run: {level-1}.   Highest: {highest}")
                        died_run = True
                        print(f"\nRun {runs} finished! \n")
                        print("Save code:", save())
                        break
        
                    c = player.c
                    cc = player.cc
                    ccc = player.ccc
        
                    # Apply Heart of Excessive Vitality penalty BEFORE fight
                    vitality_money_penalty(player)
        
                    # Add Coinpot bonus if any
                    # the actual thing is at the end of purchase, when the player press 0
                    if player.coinpot_bonus > 0:
                        if player.yd4 == 4:
                            player.coinpot_bonus *= 2
                        print(f"Coinpot bonus: +{player.coinpot_bonus:.2f} money before fight!")
                        player.money += player.coinpot_bonus
                        player.coinpot_bonus = 0
        
                    # Fight
                    if not fight(player, create_monster(level)):
                        highest = max(highest, level-1)
                        print(f"\nYou died! Level completed this run: {level-1}.   Highest: {highest}")
                        died_run = True
                        if player.money >= 25000000:
                            ac["drich"] = True
                        if player.relic == "meowton" and player.artefact == "socks":
                            ac["hmode"] = True
                            print("I don't balme you, you just attempted the hardest difficulty")
                        print(f"\nRun {runs} finished! \n")
                        print("Save code:", save())
                        
        
                        break  # exit the for-loop
                    if player.died == True:
                        player.died = False
                        break
        
                    player.c = c
                    player.cc = cc
                    player.ccc = ccc
                else:
                    # This runs only if for-loop completes (player beat level 30)
                    print("\nYou beat level 30. You win!")
                    highest = 30
                    if runs <= 3:
                        ac["trun"] = True
                        print("You beat the game with the fewest runs possible!")
                    print("Save code:", save())
                    died_run = True
                    break
        
        def sl():
            global running, event
            while running:
                code = ""
                typing = True

                while running and typing:
                    for event in pygame.event.get():
                        f()

                        if event.type == pygame.KEYDOWN:
                            if event.key == pygame.K_BACKSPACE:
                                code = code[:-1]

                            elif event.key == pygame.K_RETURN:
                                typing = False

                            else:
                                code += event.unicode

                    text_image = codef.render(code, True, (255, 255, 255))
                    screen.blit(text_image, (x, y))$
                    e()
                    pygame.display.flip()
                    #clock.tick(60)

                if code == "0":
                    return

                if load(code):
                    return

                    # if load failed, the outer while restarts
        def main():
            global runs, event, running
            
            global highest
            # Already unlocked relics
            unlocked_relics = ["family","blessed","forbidden"]
        
        # discount ticket removed!!! (set to 99999), will add back after balance later
            all_artefacts = {
                #"discount": 99999,
                "devotion": 3,
                "socks": 6,
                "coinpot": 8,
                "ar" : 17,
                "vitality": 20,
                "carrier": 20
            }
        
        #main menu mm

            act = 0
            while running:
                screen.fill(0, 0, 0)
                i($) # background
                # buttons:
                start = i($)# I will fill this in later
                ac = i($)# I will fill this in later
                lib = i($)# I will fill this in later
                cdt = i($)# I will fill this in later
                sl = i($)# I will fill this in later
                # for event in pygame.event.get():
                for event in pygame.event.get():
                    f()
                
                    if event.type == pygame.MOUSEBUTTONDOWN:
                        mouse_pos = m(event.pos)
                
                        if start.collidepoint(mouse_pos):
                            act = 1
                        elif ac.collidepoint(mouse_pos):
                            act = 2
                        elif lib.collidepoint(mouse_pos):
                            act = 3
                        elif cdt.collidepoint(mouse_pos):
                            act = 4
                        elif sl.collidepoint(mouse_pos):
                            act = 5




                print("MAIN MENU\n1 start run\n2 achievements\n3 library\n4 credits\n5 input save code\n6 obtain save code")
                #try:
                    #act = int(input("> "))
                #except ValueError:
                    #print("Invalid input, please try again.")
                    #continue
                if act == 1:
                    act = 0
                    run ()
                    continue
                if act == 2:
                    act = 0
                    pa()
                    continue
                if act == 3:
                    act = 0
                    pl()
                    continue
                if act == 4:
                    act = 0
                    #print("CREDITS\n\nI'd like to give HUGE thanks to these people, without you, this game wouldn't be possible.")
                    pc()
                    continue
                if act == 5:
                    act = 0
                    sl()
                    continue
                e()
                #pygame.display.flip()
               # clock.tick(60)
                
                    #while True:
                        #code = input("Enter save code (or 0 to cancel, there is no capital letter i): ").strip()
                    
                        #if code == "0":
                            #break
                    
                        #if load(code):
                            #break
                    
                        #print("Invalid save code. Please try again.\n")
                        #continue
                #if act == 6:
                    #print("Save code:", save())
                    #continue
                #print("Invalid input, please try again")
        
        
        main()
        print("sorry,an unknown error occurred...\nDo you mind telling me what happened?")
        print("Save code:", save())
        
finally:
    pygame.quit()
    sys.exit()
