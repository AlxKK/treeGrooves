## Model of a grove from different trees

You modeled an orange tree for our client, Farmer Fedor. It seems it was [here] [orange tree problem].
* If you haven't done this task yet, ** do it before ** before you start modeling the grove! *

Fedor was pleased with your work and therefore asked you to hop on another project. His orange farm is considering to acquire a nearby tree grove which includes a variety of trees besides orange trees.

You need to build a simple model of a grove from different trees. Start with an orange tree and use it as a reference for modeling an apple tree. Once you have two tree classes and corresponding fruit classes, refactor the code. If you don't know what refactoring is, google it. After refactoring your code, add pear trees. Finally, you can model an entire grove.

## Inheritance
In this task, you will use *inheritance* to eliminate the repetition that the `OrangeTree` and `AppleTree` classes and others create. Create a generic `FruitTree` class from which you can create more specific tree classes: orange, apple and later pear. Your general model of fruit trees will provide the standard behavior for all the trees: they grow, mature, die, etc. Orange, apple and pear trees will have the same basic characteristics but each tree will be different in its implementation: one tree produces oranges, the other - apples; one tree dies at the age of 100, the other at 45; and so on (see Table 1).


|                          | Orange trees         | Apple trees      | Pear trees       |
| ------------------------ | -------------------: | ---------------: | ---------------: |
| Maximum height           |                   25 |               26 |               20 |
| Growth rate              |                  2.5 |                2 |              2.5 |
| Annual harvest of fruits |            100 - 300 |        400 - 600 |        175 - 225 |
| Maturity age             |                    6 |                5 |                5 |
| Age of death             |                  100 |               45 |               40 |
| Diameter                 |                2-3.2 |            1-2.5 |          2.4-4.1 |
| Fruit type               |              oranges |           apples |            pears |

*Таблица 1*.  Data for orange, apple and pear trees

### Pre-release. Copy the orange tree model
Before you start, copy the code from the orange tree problem. Take the code for the orange tree and oranges. Run your tests and make sure they work as expected.

### Release 0. Apples and apple trees

You have an `OrangeTree` class that has methods like` .isMature`, `.isDead`, etc. Create an` AppleTree` class that copies this interface exactly. Your first apple tree will be no different from an orange tree.

However, even though orange trees and apple trees will behave the same, they will have different life cycles. They will produce fruit at different ages, grow at different rates, die at different times, etc. Details for each type of tree can be found in Table 1.

Start by writing tests for the `AppleTree` class. Use the orange tree tests as a reference, modifying them for the apple tree details. By the way, it is recommended to write tests for different trees in different files. Then implement the class itself. The main thing is not to confuse it, an apple tree should not produce oranges, this is against nature.

### Release 1. From specific types to general types

You have now modeled two specific types of fruit trees. Your orange and apple trees behave in a very similar way. Based on the similarities in behavior between the two types of trees, you can create a more generalized case: the fruit tree.

Create a `FruitTree` class with generic behavior. Your `OrangeTree` and` AppleTree` classes can inherit the behavior of this generic class and implement their own specifics. For example, both orange trees and apple trees grow upward. Each season the trees grow by a certain amount until they reach their maximum height. The height is different for all types, but the behavior is the same.

```javascript
class FruitTree {

}

class OrangeTree extends FruitTree {

}

class AppleTree extends FruitTree {

}

```

*Figure 1*. The definition of the `OrangeTree` and` AppleTree` classes that inherit from the `FruitTree` superclass or parent class.

Define the `FruitTree` class and change the` OrangeTree` and `AppleTree` classes to inherit from` FruitTree` (see Figure 1). Move common traits step by step from specific tree types to `FruitTree`.

As you change your code, testing your application should continue: you may need to add small changes to your tests. If your tests keep passing after refactoring, then you know that your code is fine. If not, you will quickly find your mistakes.

### Release 2. Pear and pear tress

Now that you have a generic fruit tree model from which you can derive certain types of trees, take advantage of this by creating an additional tree type: `PearTree`.

Yes, you also need to write tests for this type of tree.

### Release 3. Model of the grove 

|                          | Age 0 years | Age 5 years | Age 20 years | Age 37 years | Age 50 years | Conclusion |
| :----------------------- | ------------: | ------------: | -------------: | -------------: | -------------: | ----: |
| **Orange trees** |             0 |            20 |             20 |             10 |             20 |    70 |
| **Apple trees**     |            10 |            10 |             20 |             20 |              5 |    65 |
| **Pear tress**     |            10 |             0 |             10 |             20 |             10 |    50 |

*Figure 2*. Number of trees in the grove divided by type and age


Now that you have a model for each type of tree in the grove, let's build a model of the grove. The data for the trees in the grove are given in Table 2. You can see how many trees there are in the grove, their types and their age. Consider the example of orange trees - there are a total of 70 orange trees in the grove, 20 of them are five years old, the other 20 are 20 years old, another 10 orange trees are 37 years old, and the remaining 20 are 50 years old.

Define a `TreeGrove` class that will be responsible for all the trees in the grove. Here is a list of some of the initial functionality for the class:

1. A grove can be initialized with an array of trees.
2. A grove can return different subsets of its trees: all trees, only trees of the same type, only mature trees, etc.
3. When a tree grove passes the growing season, each of its trees passes through the `.passGrowingSeason ()` ripening season.

*Hint:* You can edit your trees. For example, you can initialize them with a given age and height.

### Release 4. Model of the expected production
It's time to use your models. Fedor wants you to report on the expected production of the grove over the next 10 seasons. For each season, your report should include:

1. How many oranges, apples and pears your model will produce each season.
2. Average size of each type of fruit.
3. For each type of tree, it is necessary to indicate how many immature, mature and dead trees are in the grove, as well as their total number (see [sample report]).


## Conclusion

In this task, you started learning about inheritance. It is a way to share behavior between similar types of objects, which can simplify your code. Inheritance is only appropriate when the subclass (for example, `OrangeTree`) is a specific type of the superclass (for example,` FruitTree`).


[example of the report]: readme-assets/example-report.md
[orange tree challenge]: ../../../orange-tree-1-just-oranges-challenge
