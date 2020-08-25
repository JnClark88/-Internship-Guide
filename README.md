# -Internship-Guide-
This guide contains all needed knowledge to simplify internship process


##Git workflow
У системы контроля версий(Git) две основных задачи:
1. Хранить информацию о всех изменениях в вашем коде, начиная с самой первой строчки
2. Обеспечение удобства командной работы над кодом.

Репозиторий Git — это место, где хранится ваш код и вся информация о его изменениях.
Репозитории могут находиться у вас на компьютере, на компьютерах ваших коллег и на удалённом сервере.

Обычно работа с Git выглядит так:

1. Сверстали шапку сайта — сделали commit;
2. Сверстали контент страницы — сделали второй commit;
3. Закончили верстать страницу — сделали третий commit и отправили код на сервер, чтобы вашу работу могли увидеть коллеги, либо чтобы опубликовать страницу;

Формат commit massage должен быть следующим ```<WorkItem number>: <короткое описание>```

Пример: ```US001: Created ComponentFactory Class```

Базовый GitFlow на большинстве проектов представлен двумя основными ветками (master и develop) и работой с ними:
* Ветка master зачастую используется для создания релизов, хранения истории о релизах и публикации их на сервере;
* Ветка develop необходима непосредственно для разработки и хранения истории работы над проектом;

Для разработки определенной фичи/фикса бага используют отдельные ветки, которые создаются на основе develop ветки.
Чтобы создать feature ветку необходимо:
1. Перейти на develop ветку
2. Создать новую ветку соблюдая правила нейминга

Формат именования feature/bugfix веток: ```feature/<workitem number>-<workitem description>```

Пример: ```feature/US001-create-component-factory``` или ```bugfix/DE001-fix-incorect-behavior```

После окончания работы в feature ветке необходимо создать Pull Request(далее PR) в Git репозиторие для дальнейшего код ревью

После код ревью и фикса всех коментариев необходимо завершить PR, после чего ваша feature ветка автоматически вмерджится в develop ветку.

При успешном мердже в develop вам необходимо будет актуализировать все остальные feature ветки, в которых ведутся работы(Если таковые имеются)

Для этого необходимо:
1. Перейти на ветку develop 
2. Обновить ветку после завершения PRа
3. Перейти на вашу feature ветку с помощью
4. Вмерджить изменения из develop ветки
5. После этого для обновления всех остальных веток необходимо повторить шаги 3 и 4 до последующего обновления develop

### Гайды по операциям с Git с помощью git bash/терминала

#### Чтобы перейти на существующую ветку необходимо:
1. Открыть терминал/git bash в корне проекта
2. Написать команду ```git checkout <имя ветки>```

#### Чтобы создать ветку в git необходимо:
1. Открыть терминал/git bash в корне проекта
2. Написать команду ```git checkout -b <имя ветки>```

#### Чтобы обновить ветку до последнего состояния необходимо:
1. Перейти в необходимую для обновления ветку
2. Выполнить команду ```git pull```

#### Для слияния одной ветки с другой необходимо:
1. Перейти в ветку, в которую вы хотите выполнить слияние
2. Выполнить команду ```git merge <имя ветки, которую необходимо вмерджить>```

### Гайды по операциям с Git с помощью Webstorm IDE

#### Чтобы перейти на существующую ветку необходимо:
> 1. ![](assets/images/git/Screenshot_43.png)
Кликнуть имя текущей ветки в нижнем правом углу
> 2. ![](assets/images/git/Screenshot_44.png)
В открытом окне выбрать из списка необходимую ветку и кликнуть по ней
> 3. ![](assets/images/git/Screenshot_45.png)
В новом сеню нажать на Checkout
> 4. После этого имя текущей ветки отобразится в нижнем правом углу

#### Чтобы создать ветку в git необходимо:
> 1. ![](assets/images/git/Screenshot_43.png)
> Кликнуть имя текущей ветки в нижнем правом углу
> 2. ![](assets/images/git/Screenshot_46.png)
> В открытом меню кликнуть на пункт New Branch
> 3. ![](assets/images/git/Screenshot_47.png)
> В модальном окне в поле New branch name задать имя ветки и кликнуть на кнопку Create.
> Если необходимости переходить на новую ветку сейчас нет то нужно убрать чекбокс Checkout branch
> 4. После этого имя новой ветки отобразится в нижнем углу, если чекбокс перехода был активен. В противном случае ветку можно найти в списке всех веток.


#### Чтобы обновить ветку до последнего состояния необходимо:
> 1. ![](assets/images/git/Screenshot_1.png)
Кликнуть на кнопку Update Project в верхнем правом углу
> 2. ![](assets/images/git/update_project_modal.png)
В модальном окне нажать Ok

Или

> 1. ![](assets/images/git/Screenshot_2.png)
>   В верхнем меню кликнуть на VCS
> 2. ![](assets/images/git/Screenshot_3.png)
> Кликнуть на Update project
> 3. ![](assets/images/git/update_project_modal.png)
> В модальном окне нажать Ok

#### Для слияния одной ветки с другой необходимо:
> 1. Перейти в ветку, в которую вы хотите выполнить слияние
> 2. ![](assets/images/git/Screenshot_43.png)
>  Кликнуть имя текущей ветки в нижнем правом углу
> 3. ![](assets/images/git/Screenshot_44.png)
> В открытом окне выбрать из списка необходимую ветку и кликнуть по ней
> 4. ![](assets/images/git/merge.png)
> В открытом меню кликнуть на пункт Merge into current

#### Для того чтобы выполнить коммит необходимо:
> 1. ![](assets/images/git/commit1.png)
>  Кликнуть на кнопку Commit в верхнем правом углу
> 2. ![](assets/images/git/commit2.png)
> В выделеном поле выбрать файлы, которые хотите закомитить
> 3. ![](assets/images/git/commit3.png)
> В следующем после написать Commit message
> 4. Нажать на кнопку Commit
> 5. Если необходимо сразу запушить изменения можно кликнуть на стрелочку рядом с кнопкой Commit
> 6. ![](assets/images/git/commit 4.png)
> В открывшемся меню кликнуть на Commit and Push...
> 7. 
