# Test2

Необходимо выполнить задание на Unreal Engine 4.26. Реализация должна быть в 3D. Все ассеты (модели, звуки, текстуры), кроме кода и блюпринтов, можете брать из любых открытых источников. Необходимо использовать принципы ООП, соблюдать стилизацию кода, блюпринты должны быть удобочитаемыми. 
!Использовать любые сторонние плагины нельзя.
Есть сцена с тремя кнопками, которые называются “1”, “2” и “3”.
На сцене расположены три “гнезда”: “гнездо-1”, “гнездо-2” и “гнездо-3”. Подразумевается, что из гнезд могут появиться черепашки.
У каждого “гнезда” есть своя точка назначения.
При нажатии кнопки “1” в “гнезде-1” появляется “черепашка-1”, которая должна прийти в движение и пройти от своей позиции вперед, до точки назначения.
При нажатии кнопки “2” в “гнезде-2” появляется “черепашка-2”, которая должна прийти в движение и тоже пройти от своей позиции до точки назначения, но по таким правилам: идет секунду вперед и на полсекунды останавливается, опять идет секунду вперед и на полсекунды останавливается, и т.д.
При нажатии кнопки “3” в “гнезде-3” появляется “черепашка-3”, которая, тоже, должна начать движение до точки назначения, но по таким правилам: идет секунду вперед и затем полсекунды назад, опять секунду вперед и полсекунды назад, и т.д.
Необходимы аудио-эффекты и визуальные эффекты при появлении, передвижении и финишировании “черепашек”. Эффекты выбираются на ваше усмотрение.
При запуске проекта, должен открываться уровень, на котором реализовано тестовое задание.
Модели “черепашек” не обязательно должны быть именно черепашками, можете использовать любые другие модели, которые сможете найти


#### Описание работы

BP_Fox(Character) имеет единственный метод Move, который действует по одному из 3 правил упомянутых в задании. Для движения используется NavMesh и метод контроллера SimpleMoveToLocation. Временные задержки реализованы с помощью Delay.

BP_SpawnPoint(Actor) содержит в себе точку спавна и точку назначения. Имеет метод SpawnFox, который спавнит лису и вызывает у неё метод Move. Лиса удаляется со сцены при достижении точки назначения посредством пересечения с CollisionBox, расположенной в точке назначения.

В начале игры автоматически спавнится HUD, который добавляет кнопки спавна на экран.
Каждая кнопка связывается с расположенными на сцене точками спавна при помощи тегов.
При нажатии кнопки вызывается метод SpawnFox соответствующей ей SpawnPoint.
Метод SpawnFox вызывает метод Move у каждой заспавненой лисы.


