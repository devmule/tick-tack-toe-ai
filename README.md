# tick-tack-toe-ai
научно-исследовательская работа на тему "искусственный интеллект"

автор: Батятин Максим (DevMule)

github: https://github.com/DevMule/tick-tack-toe-ai

цель работы: исследовать процессы проектирования и создания автоматических систем для решения конкретных задач

Я пытался выбрать для проекта простую, знакомую каждому основу что позволит мне, разрабатывая ботов, 
долгое время не доходить до состояния нераспутываемого хаоса. Мой выбор пал на древнюю игру - "херики-оники".
Прежде чем начать разрабатывать ботов, необходимо создать основу для игры.

# Игровое поле
Это оказалось нетрудно, т.к. по сути игра представляет из себя массив со значениями для каждой ячейки и функцию проверки на победу.
Другое дело - я понятия не имел чем буду ограничиваться в будущем, ведь правил и видов крестиков-ноликов есть довольно большое количество, потому исходя из этого и имеющихся на данным момент привычек сделал систему "резиновой" - поле и условие победы может быть разных размеров

### [код игрового поля](https://github.com/DevMule/tick-tack-toe-ai/blob/master/desk/desk.py)

Хорошо! Доска есть, теперь нужно сделать так, чтобы в неё можно было хотя бы играть. Нужно сделать реффери, который будет запрашивать ход у игроков и универсальный интерфейс от которого будут наследоваться игроки во имя полиморфизма!
# Реффери и Контроллер

### [код реффери](https://github.com/DevMule/tick-tack-toe-ai/blob/master/referee.py)

### [код контроллера](https://github.com/DevMule/tick-tack-toe-ai/blob/master/bots_and_uis/controller.py)

# Игроки
Под игроками я подразумеваю системы, которые будут взаимодействовать с игрой как игроки. Это боты и пользовательские интерфейсы, но никак не люди.
## консольный пользовательский интерфейс

## рандомный бот
Просто расширяет у контроллера метод хода, выдаёт случайную свободную координату. Это самый скучный и самый лёгкий игрок, 
однако даже он иногда побеждает minimax бота :)

## minimax бот
Более комплексная машина, но тоже представляет из себя только расширение метода совершения хода
Суть его содержания [понятна уже из названия](https://www.youtube.com/watch?v=KU9Ch59-4vw).
Его победить довольно сложно, однако возможно, расставляя подобные ловушки:

![ловушка джокера](https://image.prntscr.com/image/cPHTPBs8TBq2sQ1GhqOfIA.png)

Хотя, как понятно из скриншота, minimax бот сам тоже умеет их расставлять :)
