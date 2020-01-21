## Сделаем двигающиеся трубы

Далее ты сделаешь так, чтобы трубы стали двигаться по экрану для создания полосы препятствий. курса.

![трубы, двигающиеся по экрану](images/flappy-clones-test.png)

\--- task \---

Сначала сделай появление труб, добавив код к спрайту Трубы таким образом, что `когда зелёный флаг нажат`{:class="block3events"}, спрайт `повторять всегда`{:class="block3control"} `создает клон самого себя`{:class="block3control"} каждые две секунды.

![спрайт трубы](images/pipes-sprite.png)

```blocks3
когда щёлкнут по зелёному флагу
установить размер (200) %
спрятаться
повторять всегда 
  создать клон (myself v)
  ждать (2) секунд
end
```

**Совет:** клоны являются лишь только копиями спрайта, и они действительно полезны для создания игр.

\--- /task \---

\--- task \---

Затем сделай трубы двигающимися, добавив код так, что `при запуске клона` {: class = "block3control"}, клон появляется в правой части Сцены и `скользит` {: class = "block3motion"} влево.

![спрайт трубы](images/pipes-sprite.png)

```blocks3
когда я начинаю как клон
показаться
перейти в x: (240) y: (0)
плыть (4) секунд в точку x: (-240) y: (0)
удалить клон
```

**Совет:** Ты можешь остановить движение труб, нажав на красную кнопку **остановить** рядом с зеленым флагом.

\--- /task \---

Теперь у тебя должно быть много труб, но их зазоры всегда в одном и том же месте.

Ты можешь добавить немного разнообразия, используя `случайное`{: class = "block3operators"} значение для `позиции y`{: Класс = "block3motion"} спрайта Трубы.

![трубы на разных высотах](images/flappy-height-test.png)

\--- task \---

Измени код спрайта, чтобы каждый его клон `выбирал случайное число от -80 до 80`{:class="block3operators"} и `скользил`{:class="block3motion"} к его`положению по y`{:class="block3motion"}:

![спрайт трубы](images/pipes-sprite.png)

```blocks3
когда я начинаю как клон
показаться
перейти в x: (240) y: (выдать случайное от (-80) до (80))
плыть (4) секунд в точку x: (-240) y: (положение y)
удалить клон
```

\--- /task \---