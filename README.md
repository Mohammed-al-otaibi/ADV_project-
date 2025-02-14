# ADV_project-

# We will be working on a large dataset, and I will share my work on this page

# 1.Get the top 5 lowest-rated Cinema.

```
#Q1 
select name, rating
from cleaned_file
where name is not null
order by rating asc
limit 5;
```
<img width="252" alt="image" src="https://github.com/user-attachments/assets/414fdcd9-ca11-4e94-b007-e3a36ad5571f" />

# 2. We formatted to find (Park)
```
select genre, count(*) count
from cleaned_file
group by genre
having genre = "Park"
order by count desc 
```
<img width="182" alt="image" src="https://github.com/user-attachments/assets/e7edd28e-ee63-465d-9866-b28e4561e58d" />

# 3. List all Cinema in a specific city ("Riyadh").

```
select name, location 
from cleaned_file
where location like '%Riyadh%';
```
<img width="448" alt="image" src="https://github.com/user-attachments/assets/002c7125-b5d6-4eb9-ba6c-65965f416334" />


# 4. Finding Cinemas with Rating Less than or Equal 2 in Riyadh
```
SELECT name, rating, location
FROM cleaned_file
WHERE rating <= 2 AND location LIKE '%Riyadh%';
```

<img width="480" alt="image" src="https://github.com/user-attachments/assets/6ce56846-4a13-4648-9d51-8d59fad9ac38" />


# 5. Cinema that have the word ‘University’ in their name

```
select name
from cleaned_file
where name like '%University%';
```
<img width="127" alt="image" src="https://github.com/user-attachments/assets/1037416c-3a8c-44c3-b444-cdfd41225e8a" />


# 6. Finding the Most Common Location of Cinema Halls 
```
USE project;
SELECT location, COUNT(*) AS location_count
FROM cleaned_file
GROUP BY location
ORDER BY location_count DESC;
```
<img width="349" alt="image" src="https://github.com/user-attachments/assets/d43c87a3-c4c5-4021-9e1f-6a2f6ca6472d" />

# 7. Get the highest-rated Cinema in each city.

```
select name, location, rating Max_rating
from cleaned_file
where rating = (select max(rating) from cleaned_file);
```
<img width="572" alt="image" src="https://github.com/user-attachments/assets/478eb92c-1541-4a8f-b148-a57e39305340" />

# 8. Count how many Cinema have a rating of 4.

```
select count(*) Four_Star_Cinemas
from cleaned_file
where rating = 4;
```
<img width="140" alt="image" src="https://github.com/user-attachments/assets/98ab3807-6558-45f0-b25d-a9c03b9e7e82" />

# 9. Find the average rating for each genre.

```
select genre, avg(rating) avg_rating
from cleaned_file
group by genre
order by avg_rating desc;
```
<img width="199" alt="image" src="https://github.com/user-attachments/assets/a0f9887d-5f9b-4bca-84bd-c3784a6f42d5" />

# 10. Find Cinema with missing (null) best comments.

```
select name,best_comment
from cleaned_file 
where best_comment is NULL;
```

<img width="328" alt="image" src="https://github.com/user-attachments/assets/ee5dac84-ebdb-4fe5-8185-24e63efa9b6f" />


