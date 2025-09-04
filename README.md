# Coursera Course Dataset Visualization and Analysis

## Goal
The aim of this data analysis is to:

- Understand the distribution of courses certificate types, ratings, difficulties.
- Identify top courses and top course providers based on number of courses, average ratings and students enrollment.
- Explore relationship between features.

## Dataset
- **Source:** Kaggle - [Coursera Course Dataset](https://www.kaggle.com/datasets/siddharthm1698/coursera-course-dataset)
- **Description:** Dataset contains 890 course data and has 6 different columns:
  - `course_title`
  - `course_organization` - tells which organization is conducting the courses
  - `course_Certificate_type` - shows details about different certifications available in the courses
  - `course_rating` - ratings associated with each course
  - `course_difficulty` - tells what is the level of the course
  - `course_students_enrolled` - number of students enrolled in the course

**Main objective:** What makes a course popular on Coursera?

- **Project Access:** [M4S3 Project](https://colab.research.google.com/drive/1NH-TjMMJ4ThSlDy6VXw1-14mjC2bF9nm?usp=sharing)

## Method
1. Download the dataset using Kaggle API.
2. Load the data using Pandas.
3. Clean the data:
   - Drop unnecessary columns.
   - Check for missing values.
   - Check for duplicates.
   - Check for possible outliers.
4. Visualizing and analyzing the dataset using descriptive statistics and matplotlib, seaborn libraries.

## Key Insights

### Note on Outliers
Among 94 outliers, 77 courses are outliers based on the number of students enrolled. This suggests that within the 891 courses available, a subset of courses deviates significantly from the typical enrollment levels. These deviations could represent courses that are exceptionally popular (far more students enrolled than average) or, conversely, courses that are unusually unpopular (much fewer students than average).

### Distribution of data

**Certificate type**

- The most common certificate type is Course, with 582 courses. There are 297 Specializations and only 12 Professional Certificate courses. This suggests that Coursera mainly offers standard courses, while professional certificate courses make up a small portion of the platform's offerings.

<img width="498" height="397" alt="image" src="https://github.com/user-attachments/assets/93a1d889-bdbb-4329-a500-53d98a56558c" />

---

**Course ratings**

- Histogram is left-skewed, it seems that most courses have high ratings.

<img width="490" height="387" alt="image" src="https://github.com/user-attachments/assets/9d853bb8-9200-4c87-a987-5f379433a8b9" />

---

**Course difficulty**

- The most common difficulty is beginner. Intermediate and mixed show similar levels of offerings, while there are only 19 advanced difficulty courses. It seems that platform primarily offers beginner courses, with some fewer offerings for advanced learners.

<img width="496" height="399" alt="image" src="https://github.com/user-attachments/assets/9d153896-b1ad-4cf7-86f7-3ff35d7f88ad" />

---

### How does courses popularity look based on students enrolled?

**Distribution of Enrolled Students by Certificate Type**

- Enrollment in professional certificate courses is generally higher compared to specialization and standard courses. Both specialization and standard courses show a considerable number of outliers, with standard courses exhibiting slightly more extreme values.

<img width="1015" height="486" alt="image" src="https://github.com/user-attachments/assets/c404eaaa-90a0-428d-8dfe-e3d28cc0cd26" />

**Distribution of Enrolled Students by Difficulty**

- The boxplots indicate that courses with a Mixed difficulty level attract the highest student enrollment, while Advanced courses have the lowest. Beginner and Intermediate courses display similar enrollment patterns, though Beginner courses appear to be slightly more popular.

<img width="982" height="474" alt="image" src="https://github.com/user-attachments/assets/b9e8780b-295f-43bb-95fe-2c33794126b7" />

---

**Distribution of Enrolled Students by Difficulty and Certificate Type**

- An interesting observation is that there are no Mixed difficulty Professional Certificate courses, even though Mixed difficulty standard courses - the only course type available at this level - show the highest enrollments, particularly due to outliers. At the same time, Professional Certificate courses are also among the most popular overall. This paradoxical situation suggests that conclusions should be drawn with caution. Nevertheless, Beginner and Intermediate Professional Certificate courses tend to attract relatively high enrollment. Additionally, enrollment in specialization courses is generally somewhat higher than in standard courses.

<img width="980" height="479" alt="image" src="https://github.com/user-attachments/assets/ae67b0d8-f09f-4e52-8945-f00865530f7c" />

---

**Course rating by difficulty**

<img width="519" height="398" alt="image" src="https://github.com/user-attachments/assets/5f0f3800-1e80-4be8-bf1c-f4c8433b3846" />

- The boxplots further show that Beginner and Mixed difficulty courses receive similarly high ratings, while Advanced and Intermediate courses tend to have lower ratings. It is also notable that specialization courses are generally rated lower than other course types, whereas standard courses consistently achieve high ratings. Finally, Professional Certificate courses, which only exist at the Beginner and Intermediate levels, are rated fairly highly as well.

---

**Most popular courses**

- The top 5 most popular courses are Machine Learning, The Sciene of Well-Being, Python for Everybody, Programming for Everybody, Data Science. Although there is a significant gap between Machine Learning (3.5 million students) and Data Science (0.83 million students).

<img width="505" height="394" alt="image" src="https://github.com/user-attachments/assets/6cbfbb21-5d83-4a9f-81d3-7f2234c28355" />

---

**Top rated courses**

- We can see Machine Learning and The Science of Well-Being among highest rated courses too. At the same time two courses with rating 5.0 are not so popular among students.

<img width="928" height="167" alt="image" src="https://github.com/user-attachments/assets/65024f6b-142e-44ce-97fc-d9ae5a219f69" />

---

### Course provider data

**Top provider by courses offered**

<img width="506" height="388" alt="image" src="https://github.com/user-attachments/assets/2c11d6af-f1ec-4bdf-bb7e-513c9737ece4" />

- It seems that universities provide a lot of courses in Coursera.

---

**Top provider by engaged students**

<img width="561" height="398" alt="image" src="https://github.com/user-attachments/assets/969062e1-e46a-466a-912e-2d8730386a89" />

- Stanford University is the most popular based on students engaged, second is Yale University. This suggests that students tend to choose reputable course providers.

---

**Top provider by course ratings**

<img width="528" height="389" alt="image" src="https://github.com/user-attachments/assets/62f53570-a4b8-40db-a8d2-b571d61ba147" />

- The issue is that most of those ratings are very similar and barplot does not help. Thus, again I will use table to identify top provider by course ratings AND students enrolled.

<img width="570" height="293" alt="image" src="https://github.com/user-attachments/assets/ebb34a7d-4218-4652-bb91-9c0b103a115c" />

- The problem is that courses that are highest based on rating have relatively low number of courses offered and not that many students enrolled. It seems to be that it would not be the best approach to name those as best course providers. Let's look at the table if we sort by total students first and only then average rating.

<img width="489" height="284" alt="image" src="https://github.com/user-attachments/assets/fdd3d69e-9c4b-4047-9021-c920929e64df" />

- Now we can see a absolutely different view, this naturally raises a question how do I define top rated course providers?

#### How do I define best course provider?

- We have course rating, how many students are enrolled, number of courses that are provided and what type of courses are provided.
- I believe we should try to find a balance here and use weighted rating that actually depends on students enrolled. I am not sure what weight each of these variables have. This might be a good idea to discuss and decide for future projects.

---

### Correlation

<img width="644" height="493" alt="image" src="https://github.com/user-attachments/assets/8f56f184-78e7-401a-ab70-3349629a5738" />

- It seems that correlation is weak. Higher course rating does not mean that it will have highest amount of students and easier course difficulty does not mean that more students will be participating in courses. In other words, all of variables are independent of each other. However, it could be a different perspective if we include some weighted variables.

---

## Results

- **Course Difficulty:** 
  - Mixed and Beginner level courses attract the most students
- **Certificate type:** 
  - Professional Certificate and Specialization courses are the most popular, especially at Beginner and Intermediate levels
  - Mixed difficulty standard courses show highest enrollment especially due to outliers
- **Top courses:**
  - The most popular courses are related to machine learning, data science and well-being
  - Some courses with the highest available ratings are not widely enrolled
- **Top course providers:**
  - Universities are dominating in Coursera platform
  - Universities like Stanford and Yale attract the most students, suggesting that sentiment and reputation plays a significant role in student choice
  - Defining the best course provider is complex - high ratings, course counts and students enrolled numbers weights should be defined

---

## Limitations and suggestions

**Limitations**:

- Current analysis does not consider course content
- Popularity does not necessarily reflect course quality
- Weighted formulas for defining best course providers are not yet defined

**Suggestions**:

- Check why some courses fail to attract students, is it due to course ratings?
- Think about ways of defining Best Course Provider and what weights do course rating, course provider size and students enrolled have.
- After defining best course providers, prepare box plots to gather further insights and identify undoubtedly the best course provider there is before actually choosing a course.
- There is a possibility that courses popularity might be based on a sentiment too, for example Stanford university is very prestige and well known, thus students might pick courses based on already known reputation
