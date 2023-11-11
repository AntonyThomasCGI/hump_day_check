#!/usr/bin/env python3
# -*- coding: utf-8 -*-
# -----------------------------------------------------------------------------
'''

    🐫 This script checks if it is hump day 🐫

    Usage:
        - In your shell type: /path/to/script/folder/
        - Press ctrl+shift+u in your shell to enter unicode mode.
        - Type 1f42b + enter.

    Script.......Antony Thomas
    Animation....Natasha Bishop

'''
# -----------------------------------------------------------------------------

import os
import time
import random
import argparse

from datetime import datetime
from datetime import timedelta


WEDNESDAY = 2

CAMEL_SURPRISE = [
 'ICAgICAgICAgICAgICAgIF9fLS1fXyAgICAgICAgICAKICBfX18vKSAgICAgICAgLyAgICAgIFwg'
 'ICAgICAgICAKL19fIDAgXCAgICBfX18vICAgICAgICBcX18gICAgICAKICAgXCAgIFxfXy8gICAg'
 'ICAgICAgICAgICBcXyAgICAKICAgIFwgICAgICAgSEFQUFkgSFVNUCBEQVkhIFwgICAKICAgICBc'
 'dnZ2dnZcICAgICAgICAgICAgICAgIHx8ICAKICAgICAgICAgICAgXCAgL3Z2dnZ2dnZ2XF8gIHxc'
 'XCAKICAgICAgICAgICAgIC8vXFwgICAgICAgICAvL1xcViAKICAgICAgICAgICAgLy8gIFxcICAg'
 'ICAgIC8vICBcXCAKICAgICAgICAgICAvLyAgICBcXCAgICAgLy8gICAgXFwKICAgICAgICAgKF8v'
 'ICAgIChfLyAgIChfLyAgICAoXy8=', 'ICAgICAgICAgICAgICAgIF9fLS1fXyAgICAgICAgICAK'
 'ICBfX18vKSAgICAgICAgLyAgICAgIFwgICAgICAgICAKL19fIDAgXCAgICBfX18vICAgICAgICBc'
 'X18gICAgICAKICAgXCAgIFxfXy8gICAgICAgICAgICAgICBcXyAgICAKICAgIFwgICAgICAgSEFQ'
 'UFkgSFVNUCBEQVkhIFwgICAKICAgICBcdnZ2dnZcICAgICAgICAgICAgICAgIHx8ICAKICAgICAg'
 'ICAgICAgXCAgL3Z2dnZ2dnZ2XF8gIHxcXCAKICAgICAgICAgICAgIFxcICAgICAgICAgICBcIHwg'
 'ViAKICAgICAgICAgICAgLy98ICAgICAgICAgICAgfHxcXCAKICAgICAgICAgICAoX3x8ICAgICAg'
 'ICAgICAgfHwgfHwKICAgICAgICAgICAgKF8vICAgICAgICAgICAoXy8oXy8=', 'ICAgICAgICAg'
 'ICAgICAgIF9fLS1fXyAgICAgICAgICAKICBfX18vKSAgICAgICAgLyAgICAgIFwgICAgICAgICAK'
 'L19fIDAgXCAgICBfX18vICAgICAgICBcX18gICAgICAKICAgXCAgIFxfXy8gICAgICAgICAgICAg'
 'ICBcXyAgICAKICAgIFwgICAgICAgSEFQUFkgSFVNUCBEQVkhIFwgICAKICAgICBcdnZ2dnZcICAg'
 'ICAgICAgICAgICAgIHx8ICAKICAgICAgICAgICAgXCAgL3Z2dnZ2dnZ2XF8gIHxcXCAKICAgICAg'
 'ICAgICAgIC8vXFwgICAgICAgICAvL1xcViAKICAgICAgICAgICAgLy8gIFxcICAgICAgIC8vICBc'
 'XCAKICAgICAgICAgICAvLyAgICBcXCAgICAgLy8gICAgXFwKICAgICAgICAgKF8vICAgIChfLyAg'
 'IChfLyAgICAoXy8=', 'ICAgICAgICAgICAgICAgIF9fLS1fXyAgICAgICAgICAKICBfX18vKSAg'
 'ICAgICAgLyAgICAgIFwgICAgICAgICAKL19fIDAgXCAgICBfX18vICAgICAgICBcX18gICAgICAK'
 'ICAgXCAgIFxfXy8gICAgICAgICAgICAgICBcXyAgICAKICAgIFwgICAgICAgSEFQUFkgSFVNUCBE'
 'QVkhIFwgICAKICAgICBcdnZ2dnZcICAgICAgICAgICAgICAgIHx8ICAKICAgICAgICAgICAgXCAg'
 'L3Z2dnZ2dnZ2XF8gIHxcXCAKICAgICAgICAgICAgIHx8XCAgICAgICAgICBcXHwgViAKICAgICAg'
 'ICAgICAgIHx8XFwgICAgICAgICAvL3wgICAKICAgICAgICAgICAgIC98IHx8ICAgICAgKF98fHwg'
 'ICAKICAgICAgICAgICAgKF8vKF8vICAgICAgICAoXy8=', 'ICAgICAgICAgICAgICAgIF9fLS1f'
 'XyAgICAgICAgICAKICBfX18vKSAgICAgICAgLyAgICAgIFwgICAgICAgICAKL19fIDAgXCAgICBf'
 'X18vICAgICAgICBcX18gICAgICAKICAgXCAgIFxfXy8gICAgICAgICAgICAgICBcXyAgICAKICAg'
 'IFwgICAgICAgSEFQUFkgSFVNUCBEQVkhIFwgICAKICAgICBcdnZ2dnZcICAgICAgICAgICAgICAg'
 'IHx8ICAKICAgICAgICAgICAgXCAgL3Z2dnZ2dnZ2XF8gIHxcXCAKICAgICAgICAgICAgIC8vXFwg'
 'ICAgICAgICAvL1xcViAKICAgICAgICAgICAgLy8gIFxcICAgICAgIC8vICBcXCAKICAgICAgICAg'
 'ICAvLyAgICBcXCAgICAgLy8gICAgXFwKICAgICAgICAgKF8vICAgIChfLyAgIChfLyAgICAoXy8='
 '', 'ICAgICAgICAgICAgICAgIF9fLS1fXyAgICAgICAgICAKICBfX18vKSAgICAgICAgLyAgICAg'
 'IFwgICAgICAgICAKL19fIDAgXCAgICBfX18vICAgICAgICBcX18gICAgICAKICAgXCAgIFxfXy8g'
 'ICAgICAgICAgICAgICBcXyAgICAKICAgIFwgICAgICAgSEFQUFkgSFVNUCBEQVkhIFwgICAKICAg'
 'ICBcdnZ2dnZcICAgICAgICAgICAgICAgIHx8ICAKICAgICAgICAgICAgXCAgL3Z2dnZ2dnZ2XF8g'
 'IHxcXCAKICAgICAgICAgICAgIHx8ICAgICAgICAgICBcIFxcViAKICAgICAgICAgICAgL3x8ICAg'
 'ICAgICAgICAgfHxcXCAKICAgICAgICAgICAoX3x8ICAgICAgICAgICAgfHwgfHwKICAgICAgICAg'
 'ICAgKF8vICAgICAgICAgICAoXy8oXy8=', 'ICAgICAgICAgICAgICAgIF9fLS1fXyAgICAgICAg'
 'ICAKICBfX18vKSAgICAgICAgLyAgICAgIFwgICAgICAgICAKL19fIDAgXCAgICBfX18vICAgICAg'
 'ICBcX18gICAgICAKICAgXCAgIFxfXy8gICAgICAgICAgICAgICBcXyAgICAKICAgIFwgICAgICAg'
 'SEFQUFkgSFVNUCBEQVkhIFwgICAKICAgICBcdnZ2dnZcICAgICAgICAgICAgICAgIHx8ICAKICAg'
 'ICAgICAgICAgXCAgL3Z2dnZ2dnZ2XF8gIHxcXCAKICAgICAgICAgICAgIC8vXFwgICAgICAgICAv'
 'L1xcViAKICAgICAgICAgICAgLy8gIFxcICAgICAgIC8vICBcXCAKICAgICAgICAgICAvLyAgICBc'
 'XCAgICAgLy8gICAgXFwKICAgICAgICAgKF8vICAgIChfLyAgIChfLyAgICAoXy8=', 'ICAgICAg'
 'ICAgICAgICAgIF9fLS1fXyAgICAgICAgICAKICBfX18vKSAgICAgICAgLyAgICAgIFwgICAgICAg'
 'ICAKL19fIDAgXCAgICBfX18vICAgICAgICBcX18gICAgICAKICAgXCAgIFxfXy8gICAgICAgICAg'
 'ICAgICBcXyAgICAKICAgIFwgICAgICAgSEFQUFkgSFVNUCBEQVkhIFwgICAKICAgICBcdnZ2dnZc'
 'ICAgICAgICAgICAgICAgIHx8ICAKICAgICAgICAgICAgXCAgL3Z2dnZ2dnZ2XF8gIHxcXCAKICAg'
 'ICAgICAgICAgIHxcXCAgICAgICAgICBcfHwgViAKICAgICAgICAgICAgIHx8XFwgICAgICAgICAv'
 'fHwgICAKICAgICAgICAgICAgIC98IHx8ICAgICAgKF98fHwgICAKICAgICAgICAgICAgKF8vKF8v'
 'ICAgICAgICAoXy8gICA='
]


def it_is_wednesday_my_dudes():
    """Alexa play Camel by Camel by Sandy Marton.
    """
    import curses
    import base64

    camel_anim = [base64.b64decode(x).decode('utf-8') for x in CAMEL_SURPRISE]

    screen = curses.initscr()
    curses.raw()
    curses.curs_set(0)

    y_max, x_max = screen.getmaxyx()
    y_start = y_max // 2 - 5 if y_max > 10 else 0

    for i in range(1, x_max):
        frame = camel_anim[(i % (5 * len(camel_anim))) // 5]
        x_pos = x_max - i
        screen.clear()
        for j, scan_line in enumerate(frame.split('\n')[:y_max - 1]):
            screen.addstr(y_start + j, x_pos, scan_line[:i])
        screen.refresh()
        time.sleep(0.06)

    for k in range(1, 32):
        frame = camel_anim[((i + k) % (5 * len(camel_anim))) // 5]
        screen.clear()
        for j, scan_line in enumerate(frame.split('\n')[:y_max - 1]):
            screen.addstr(y_start + j, 0, scan_line[k:])
        screen.refresh()
        time.sleep(0.06)

    curses.endwin()

    print('happy hump day 🐫 !')


def time_since_wednesday(today: datetime):
    if today.weekday() in [5, 6]:
        percent_since = 1.0
    else:
        time = timedelta(
            hours=today.hour,
            minutes=today.minute,
            seconds=today.second,
            microseconds=today.microsecond,
        )
        time_since_hump = timedelta(days=today.weekday() - 3) + time
        seconds_since_hump = time_since_hump.total_seconds()
        percent_since = seconds_since_hump / timedelta(days=2).total_seconds()

    terminal_width, _ = os.get_terminal_size(0)
    sand_width = terminal_width - 32

    sand = '....:         '
    sand_gen = ''.join([random.choice(sand) for i in range(sand_width)])
    camel_location = int(percent_since * sand_width)

    today_formatted = f'{today:%A %I:%M %p}'
    if percent_since < 0.5:
        today_padding = ' ' * (camel_location) + '↓ ' + today_formatted + \
            ' ' * (sand_width - camel_location - len(today_formatted))
    elif percent_since < 1.0:
        today_padding = ' ' * (camel_location - len(today_formatted)) + \
            today_formatted + ' ↓' + ' ' * (sand_width - camel_location)
    else:
        today_padding = ' ' * (sand_width + 5 - len(today_formatted)) + \
            today_formatted + ' ↓'

    if percent_since == 1.0:
        print('You made it camel, enjoy weekend!')
        print('                  ' + today_padding)
        print('.🌴 .🌴wednesday🌴' + sand_gen + '🌈week🐫end🌈')
    else:
        print('You almost made it camel, weekend awaits!')
        print('                  ' + today_padding)
        print(
            '.🌴 .🌴wednesday🌴' + sand_gen[:camel_location] + '🐫' +
            sand_gen[camel_location + 1:] + '🌈weekend🌈'
        )


def time_until_wednesday(today: datetime):
    time = timedelta(
        hours=today.hour,
        minutes=today.minute,
        seconds=today.second,
        microseconds=today.microsecond,
    )
    time_until_hump = timedelta(days=2 - today.weekday()) - time
    seconds_until_hump = time_until_hump.total_seconds()
    percent_away = 1 - seconds_until_hump / timedelta(days=2).total_seconds()

    terminal_width, _ = os.get_terminal_size(0)
    sand_width = terminal_width - 22

    sand = '....:         '
    sand_gen = ''.join([random.choice(sand) for i in range(sand_width)])
    camel_location = int(percent_away * sand_width)

    days = time_until_hump.days
    hours = time_until_hump.seconds // 3600
    minutes = (time_until_hump.seconds // 60) % 60
    seconds = time_until_hump.seconds % 60
    if days:
        time_formatted = f"{days} day{('' if days == 1 else 's')} " + \
            f"{hours} hour{('' if hours == 1 else 's')} " + \
            f"{minutes} minute{('' if minutes == 1 else 's')} " + \
            f"{seconds} second{('' if seconds == 1 else 's')} away."
    else:
        time_formatted = f"{hours} hour{('' if hours == 1 else 's')} " + \
            f"{minutes} minute{('' if minutes == 1 else 's')} " + \
            f"{seconds} second{('' if seconds == 1 else 's')} away."

    today_formatted = f'{today:%A %I:%M %p}'
    if percent_away > 0.5:
        today_padding = ' ' * (camel_location - len(today_formatted)) + \
            today_formatted + ' ↓' + ' ' * (sand_width - camel_location)
    else:
        today_padding = ' ' * (camel_location) + '↓ ' + today_formatted + \
            ' ' * (sand_width - camel_location - len(today_formatted))

    print('Keep pacing along camel, Wednesday awaits!')
    print(' ' * (terminal_width - len(time_formatted)) + time_formatted)
    print(today_padding + '           ↓      ')
    print(
        sand_gen[:camel_location] + '🐫' +
        sand_gen[camel_location + 1:] + '.🌴 .🌴wednesday🌴'
    )


def main() -> int:
    parser = argparse.ArgumentParser('camel')
    parser.add_argument('--force-wednesday', action='store_true')
    args = parser.parse_args()

    today = datetime.now() if not args.force_wednesday else WEDNESDAY

    if today == WEDNESDAY:
        it_is_wednesday_my_dudes()
    elif today.weekday() < WEDNESDAY:
        time_until_wednesday(today)
    else:
        time_since_wednesday(today)

    return 0


if __name__ == '__main__':
    raise SystemExit(main())
