---
docid: intro
title: What is Litho?
layout: docs
permalink: /docs/intro
---

Litho - это декларативный фреймворк для создания эффективных пользовательских интерфейсов (UI) для Android. 
Он позволяет описывать высокооптимизированные представления, используя простое функциональное API, 
основанное на аннотациях Java. Фреймворк был [изначально спроектирован](/docs/uses) для описания 
сложных пролистываемых интерфейсов, основанных на RecyclerView.

С фреймворком Litho вы оперируете *компонентами*, не взаимодействуя напрямую 
с традиционными представлениями Android. По сути, *компонент* - это функция, 
принимающая неизменяемые входные значения (*props*) и возвращающая иерархию компонентов, 
отражающую ваш интерфейс

```java
@LayoutSpec
class HelloComponentSpec {

  @OnCreateLayout
  static ComponentLayout onCreateLayout(
      ComponentContext c,
      @Prop String name) {

    return Text.create(c)
        .text("Hello, " + name)
        .textSizeRes(R.dimen.my_text_size)
        .textColor(Color.BLACK)
        .withLayout()
        .paddingDip(ALL, 10)
        .build();
  }
}
```

Вы просто указываете, что вы хотите показать - а Litho обеспечивает наиболее 
эффективный способ отображения за счет расчетов [расположения элементов в фоновом потоке](/docs/asynchronous-layout), 
автоматического [сглаживания иерархии](/docs/view-flattening) и [инкрементальной отрисовки](/docs/inc-mount-architecture) сложных компонентов.

## Посмотрите презентацию с F8

<a href="https://developers.facebook.com/videos/f8-2017/litho-a-declarative-framework-for-efficient-uis/" target="_blank">
  <img src="{{ '/static/images/f8-intro.png' | relative_url }}">
</a>

## Продолжайте изучать

В нашем [самоучителе](/docs/tutorial) вы найдете пошаговую инструкцию по использованию 
Litho в вашем приложении. Вы также можете прочитать статьи о том, как [писать](/docs/writing-components) 
и [применять](/docs/using-components) ваши собственные компоненты Litho в нашем кратком руководстве.
