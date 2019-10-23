# code-challenges
Happy coding :)

## Before you start ##
- You do not need to complete all the challenges in a given time
- Please complete a challenge with most detailed as you can
- You can use the internet and your favor IDE
- For Java challenges, we would love to see fully running code
- For Design challenges, answer not limit to text, you can use diagrams to demonstrate your answer
- There may have variants you would like to inquiry during the challenges, 
but let assume that all the information you could have and try to provide solutions that take these variants into account.
- **How to submit your answers:**
  - Create a Git repo, and send us your repo link (prefer way)
  - Or upload into a cloud drive and send us granted permission link 
  - Or zip your solution and send via email (not prefer for big file size)
  - Please help to note which challenges you has completed in the reply email 

## Java Challenges ##
### Challenge 1 ###
Please write a Java method that receive the input as a list of `Integer` and return its sum by using **recursive**

### Challenge 2 ###
Given a list of `n` `Integer`, it is called Dol Flip if
the list can be split into 2 parts, `[0, i]` and `[i, n-1]` that
- Within a part, it is sorted either `ASC` or `DESC`
- 2 parts's sorted order is opposite, e.g first part sorted with `ASC`, the second part sorted with `DESC`

The `i` is call the Flip point.

Samples:
- Given the DolFlip list `[5, 7, 9, 3, 2]`, Flip point is `2`
- Given the DolFlip list `[9, 7, 6, 5, 6]`, Flip point is `3`

Write a Java method, input a Dol Flip list and return the Flip point.

Please try to provide most optimal solution as you can.

**Note:**
- You can assume the list is always a Dol Flip list.
- `n` range `[3, 2147483647]`

### Challenge 3 ###
We have a `Book` Entity with has 2 `String` properties `name` and `author`, please design **REST APIs specification** for CRUD `Book` entity

### Challenge 4 ###
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

### Challenge 5 ###
Given this mobile design:

![Alt text](resources/search-bar.png?raw=true "Search Bar")

With JPA and Hibernate for PostgreSQL database. Let’s define entity models or database design diagrams to adapt this design

### Challenge 6 ###
How can you detect **memory issue** of your Java application and how to solve it?

## Design challenges ##
Let assume we are about to develop an eLearning platform similar to Udemy but focusing on English learning, the platform has 3 primary groups of users:
- End-user: who use the platform to learn new things
- Tutor: who register as a tutor and prepare materials for online courses Or private lesson tutor.
- Admin: who in-charge of system operations and daily admin tasks

The product would require:
- Support multiple platforms e.g. web, mobile and tablet
- User does not require login to use some of the features like browsing courses, view preview materials, etc
- User can login with Facebook, Google or register their own account
- Payment will be integrate with 3rd party provider
- All courses materials would be life-time access
- Tutors will able to create their course, prepare material, and register free slot for private English lesson 
- The course materials uploaded by Tutor will be reviewed by Admin before available to end users
- Support VOD for courses and live streaming for private tutor lessons
- Able to launch marketing campaign and allow discount if any
- Strongly require UI consistency and provide best UX as much as possible
- Primary audience will be in Vietnam
- Admin and Tutor should able operate their daily tasks easily, only webapp is required for Admin and Tutor 
- Support mobile push notification and SMS notification
- Tracking user events for user recommendation and BI reports

Notes:
- Nice if the solution approach with microservices
- For critical components please provide in detailed eg. which exactly service or framework is used
- Traffic would be dramatically increase during sale
- All below challenges share the same context but can be delivered independently

### Challenge 6 ###
Please provide high-level components diagram and deployment diagram for this system.

*For critical components please provide in detailed*

### Challenge 7 ###
We would like to deliver new updates within every 2-weeks. New updates rollout should not cause any business interruption. 
Some services could have shorter release period than others. 

Please help to provide the solution to cover this requirement but still ensure quality between releases (in detailed).

### Challenge 8 ###
Assume we need to deliver a big feature which require 2-3 months development effort across services and teams. 
During this period, small/medium features still be released as usual e.g. every 1-2 weeks. 
Features would be functional related/impact to each others e.g. a small feature could impact and require business logic update on the big feature.

Please give your advise how to deliver these features in plan which still ensure the quality of the product

### Challenge 9 ###
How would you deal with cybersecurity attacks in general and in specific to DDoS for this system?
