# Як розробити додаток для IOS ?
### Актуальність
За статистикою 2020 року найбагатша компанія світу є Apple ($241,2 млрд, зростаня на 17% за рік).
При цьому саме iPhone приносить 60% доходу компанії. Отже створення додаткового софту для цього девайсу є досить актуальною та прибутковою справою сьогодні.

### Постановка завдання
Один з ключових факторів, який зробив Apple найбагатшою компанією світу - це підхід "все своє". Якщо бути точним: свої девайси(IPhone, IPad, Macbook), свої операційні системи(IOS/MacOs), свій єдиний магазин додатків (AppStore) і тд. Також, кожен бажаючий створити додаток для операційних систем Apple, може зробити це лише на мові, яку розробила безпосередньо сама компанія - мова Swift. 
Оскільки найпопулярнішою одиницею продукту компанії є IPhone, то додаток ми будемо писати для операційної системи IOS. Середовище для розробки єдине - XCode. Найкращий фреймворк для створення інтерфейсу для користувача за словами самої компанії є SwiftUI. Довіримось професіоналам.
Цікаво буде перевірити:
- Роботу з віджетами SwiftUI
- Роботу із зображеннями
- Написати власний ігровий алгоритм 

Додаток, який буде перевіряти знання прапорів різних країн та виведе результат користувача вкінці - чудовий додаток для новачка, який дозволить пройти усі вище вказані пункти. 

###  Необхідні знання 
Весь проект буде написаний виключно на Swift, проте вона є достатньо легкою для опанування програмістам з базою Python/Java. Мова є відносно молодою,тому вона увібрала в себе все найкраще від своїх попередників. 
Для розробки бажаного додатку нам необхідно знати як створити наступні віджети(додані посилання на офіційну документацію сайта Apple):
- [Text](https://developer.apple.com/documentation/swiftui/text)
- [Image](https://developer.apple.com/documentation/swiftui/image)
- [Button](https://developer.apple.com/documentation/swiftui/button)
- [Загальна документація SwiftUI](https://developer.apple.com/documentation/swiftui)



### Середовище розробки
XCode є дуже зручним середовищим для стоворення додатку. Як тільки ми заходимо в програму, XCode одразу пропонує нам декілька готових шаблонів додатків (Game, Augmented Reality App, Document Based App і тд). Для реалізації нашого завдання нам ідеально підходить шаблон Single View App.
![alt text](https://github.com/arturvypovskyy/Swift_Projects/blob/main/Снимок%20экрана%202021-05-24%20в%2016.55.55.png)

Шаблон уже має в собі наступний код

```
import SwiftUI

struct ContentView: View {
    var body: some View {
        Text("Hello, World!")
    }
}

struct ContentView_Previews: PreviewProvider {
    static var previews: some View {
        ContentView()
    }
}
```
 Писати свій код ми будемо безпосердньо в структурі ContentView.
 XCode влаштований так, що зліва ми бачимо впорядкований по папкам щойно створений проект, посередині ми маємо редактор кода, а зправа  Canvas, на якому ми бачимо візуальні зміни інтерфейсу додатка в реальному часі, що робить створення додатка набагато швидшою та зручнішою справою.
 ![alt text](https://github.com/arturvypovskyy/Swift_Projects/blob/main/Снимок%20экрана%202021-05-24%20в%2017.13.27.png)
 
 ### Реалізація 
 1. Спочатку створимо градієнтний фон для приємного перегляду контенту.
 ![alt text](https://github.com/arturvypovskyy/Swift_Projects/blob/main/Снимок%20экрана%202021-05-24%20в%2017.55.17.png)
 2. Додамо два віджета Text: "Cчет:" та "Выбери флаг:"


  ![alt text](https://github.com/arturvypovskyy/Swift_Projects/blob/main/Снимок%20экрана%202021-05-24%20в%2018.00.01.png)
 
3. Створимо віджети Image, але з функціями віджета Button та розробимо ігровий алгоритм.
``` Button(action:{
                        if(number == self.correctAnswer){
                            self.gameCount += 1
                        }
                        self.countriesWere.append(self.countries[self.correctAnswer])

                        if(self.countriesWere.count < 10){

                        self.countries.shuffle()
                        repeat{
                            self.correctAnswer = Int.random(in: 0 ..< 3)
                            self.countries.shuffle()

                        }while(self.countriesWere.contains(self.countries[self.correctAnswer]) || (self.countriesWere.contains(self.countries[0]) && self.countriesWere.contains(self.countries[1]) && self.countriesWere.contains(self.countries[2])))

                        }


                    }){
                        Image(self.countries[number])
                            .renderingMode(.original)
                            .frame(width: 250, height: 130)
                            .clipShape(Rectangle())
                            .overlay( Rectangle()
                                .stroke(Color.black, lineWidth: 3))
                    }
 ```
 
 ![alt text](https://github.com/arturvypovskyy/Swift_Projects/blob/main/Снимок%20экрана%202021-05-24%20в%2018.42.45.png)

4. Запускаємо та перевіряємо роботу додатка

![video](https://user-images.githubusercontent.com/71068169/119405380-d6ad1000-bce9-11eb-9d90-bda20937b09d.mov)

### Висновок
В результаті виконаної роботи, ми створили додаток, який чудово справляється з поставленою задачою і навіть готовий до загрузки в магазин AppStore. Отримані навики та знання є безперечно корисними в майбутньому при створені інших додатків та ігор. Завдяки зручному софту від Apple та відмінної синхронізації девайсів - розробка пройшла швидко та з задоволенням.



