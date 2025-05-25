# The Analysis

## 1. What are the most demanded skills for the top 3 most popular data roles?

To find the most demanded skills for the top 3 most popular data roles: I filtered out those positions by which ones were the most popular, then got the top 5 skills for these top 3 roles. This query highlights the most popular job titles and their top skills, showing which skills I should pay attention to depending on the role I'm targeting.

View my notebook with detailed steps here: [2_Skill_Demand.ipynb](3_Project\2_Skills_Count.ipynb)

### Visualize Data

```python
fig, ax = plt.subplots(len(job_titles), 1)

for i, job_title in enumerate(job_titles):
    df_plot = df_skills_count[df_skills_count['job_title_short'] == job_title].head(5)
    df_plot.plot(kind='barh', x='job_skills', y='skill_count', ax=ax[i], title=job_title)
    ax[i].invert_yaxis()
    ax[i].set_ylabel('')
    ax[i].legend().set_visible(False)

fig.suptitle('Counts of Top Skills in Job Postings', fontsize=15)
fig.tight_layout()
plt.show()
```

### Results

![Visualization of most demanded skills for top 3 roles in Mexico](3_Project\Images\skills_in_demand_top3_roles.png)

### Insights

- Python appears on the top 3 data roles in Mexico, proving to be a versatile skill and highly demanded across these roles. However it's more prominent for Data Engineers (62%) and Data Scientists (62%).
- SQL is the most requested skill for Data Analysts (44%) and Data Engineers (68%), coming in second for Data Scientist with 57% of demand. Python is the most sought-after skill for Data Scientists, making an appearence in 62% of job postings.
- Data Engineers require more specialized technical skills such as AWS, Azure, and Spark compared to Data Analysts and Data Scientists who are expected to be proficient in more general data management and analysis tools such as Excel, and Tableau.