# code-challenges

## Challenge 1 ##
Please write a Java method that receive the input as a list of `Integer` and return its sum by using **recursive**

## Challenge 2 ##
Given a list of `n` `Integer`, it is called Dol Flip if
the list can be split into 2 parts, `[0, i]` and `[i, n-1]` that
- Within a part, it is sorted either `ASC` or `DESC`
- 2 parts's sorted order is opposite, e.g first part sorted with `ASC`, the second part sorted with `DESC`

The `i` is call the Flip point.

Samples:
- Given the DolFlip list `[5, 7, 9, 3, 2]`, Flip point is `2`
- Given the DolFlip list `[1, 3, 5, 8, 3]`, Flip point is `3`

Write a Java method, input a Dol Flip list and return the Flip point. You can assume the list is always a Dol Flip list. What is the complexity of your method.

## Challenge 3 ##
We have a `Book` Entity with has 2 properties `name` and `author`, please design REST APIs specification for CRUD `Book` entity

## Challenge 4 ##
Given this code snippets using JPA and Hibernate:
```
@Entity
@Inheritance(strategy = InheritanceType.SINGLE_TABLE)
public class Assignment {
  @Id
  @GeneratedValue
  private Long id;

  @Enumerated(EnumType.ORDINAL)
  @Column(name = "type", nullable = false)
  private AssignmentType type;

  @Column(name = "title")
  private String title;

  @Column(name = "question")
  private String question;

  // getters setters
}

@Entity
public class WritingAssignment extends Assignment {
  @Column(name = "word_limit")
  private Long wordLimit;

  @Column(name = "answer")
  private String answer;

  // getters setters
}

@Entity
public class SpeakingAssignment extends Assignment {
  @Column(name = "time_limit")
  private Long timeLimit;

  @Column(name = "question_audio_url")
  private String questionAudioUrl;

  @Column(name = "answer_audio_url")
  private String answerAudioUrl;

  // getters setters
}

public class AssignmentDTO {
  private Long id;
  private AssignmentType type;
  private String title;
  private String question;
  private String questionAudioUrl;
  private Long limit; // common limit for both writing and speaking
  private String answer; // common answer for both writing and speaking
  
  // getters setters
}

public enum AssignmentType {
  WRITING,
  ASSIGNMENT
}
```
1/ Please write **only 1 sql query** to retrieve all writing assignments and speaking assignments with all properties satisfied AssignmentDTO

2/ The same as above but with different inheritance strategy
``@Inheritance(strategy = InheritanceType.JOINED)``

**Note**: You can use SQL native or JPQL syntax as what you prefer

## Challenge 5 ##
Given this mobile design:

![Alt text](resources/search-bar.png?raw=true "Search Bar")

With JPA and Hibernate for PostgreSQL database. Let’s define entity models or database design diagrams to adapt this design

## Challenge 6 ##
As a food delivery company, we want to develop an application to help customer to place food or drink orders at food court by mobile or web application, then shipper will deliver them to our customer on time like Foody, Grab, Go-Viet are doing now. We also support online payment by 3rd-party e-wallet provider. 

Based on this requirement, we want to build a microservices ecosystem. Lets decompose application into backend services as much as you can that need to develop for this business flow. Please draw a diagram with service names and their responsibilities for easily understand

