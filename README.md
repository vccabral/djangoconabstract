Title
===
Every Mistake Possible with the Django ORM


Description
===
The Django Object Relational Map (ORM) is a powerful tool that has had several new advances. After using the ORM for over 5 years, I have identified 60 tips, traps, and debugging techniques that are built on top of moments of insight, reading the Django source code, and mostly tearing my hair out trying to make the ORM behave.



Detailed Abstract
===

Introduction
--------
As a developer, I have failed. I have failed many times and each failure has been an opportunity to learn something new. My knowledge of the django ORM consists of battle scars and these tips and tricks serve as a public invitation to learn from my pain instead of your own. 

Tools
-----
Several tools have proven invaluable for debugging, ad hoc experimentation, and for impressing the end users. I will go over powerful code snippets, third party apps for beautifying the admin, and must use debugging tools for quick querying, identifying performance issues, and viewing data and models. 

Conventions
-----------
Several conventions arise from using the ORM on a daily basis. I will outline the most important steps to limit over querying, displaying data in a sensical format to the end users with least effort, and designing your models to reduce code and validate data effectively. 

Data Modeling
-----------
Model design ranks near the top in a well defined project. When to use OneToOne, meta classes unique with, null vs blank, Foreign keys, Many to Many relations using through versus rolling your own through model design and much more. Remember, data structures inform the future developers what your application does. Model design, in many ways, defines your project more than the code. 

Performance
------------------
Don't query result sets in the templates. When using the django rest framework, override the get_queryset to include select_relate or prefetch_related if nesting your serializers. Use the django debug tool bar to identify where over querying occurs. I will discuss all of these and more tips for making the ORM behave the way expect so you don't end up casting a queryset to a list. Many of you will know the basic optimization so I will also dive deep into esoteric performance problems that only occur with scale. 

Deploying to PaaS
-----------------
If you have deployed to heroku, you will understand a few pain points to deploying including what can go wrong with migrations on a production system that didn't go wrong on your local environment.  I will explain the subtle differences and problems that arise in the djano ORM from deploying your code to Platforms as a Service including a brief aside in getting django running on elastic beanstalk for less than half the price of heroku with all the support of AWS. 

Migrations
----------
Mysql does not support acid schema transactions. SQLite doesn't either but the core developers used several tricks to get around that. There are also now more effective ways to import data aside from fixtures which have proven to be brittle in the past. Ultimately, migrations improve the usefulness of django but there are several traps to avoid and I will highlight the lessons I have learned.
