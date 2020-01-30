---
layout: post
title:      "Rails Project - MedList"
date:       2020-01-30 18:56:09 +0000
permalink:  rails_project_-_medlist
---

This project was very challenging, but I learned alot! I was a bit nervous and overwhelmed about starting this project as all the knowledge learned from the entire Rails section was being put to the test and applied to this project. There were tons of 'Aha!' moments and the areas that I fully didnt understand before were solidified from my trial and errors while building out the application

For this project, I wanted to focus on creating an application that was quite meaningful to me and that anyone could use including myself. Coming from the medical field, I see alot of patients both young and old taking numerous medications and supplements but have no clue as to what they are taking and not knowing the reason as to why they are taking it. Anyone could greatly benefit from having all of their medications in one place for quick reference. 



**MedList**

The most challenging part before tackling this project was deciding on my models and that their associations were set up correctly in order for the application to work the way I wanted it to. The models used were User, Medication, Condition, and Category with the following associations: 

**User**
```
has_many :conditions
has_many :conditioned_medications, through: :conditions, source: :medication
has_many :medications
has_many :categories, through: :medications
```

**Medication**
```
belongs_to :user
belongs_to :category
has_many :conditions
has_many :users, through: :conditions
```

**Condition**
```
belongs_to :user
belongs_to :medication
```

**Category**
```
has_many :medications
has_many :users, through: :medications
```

After getting my associations the way I wanted, then on to Active Record to build my migrations.

```
ActiveRecord::Schema.define(version: 2020_01_15_010531) do

  create_table "categories", force: :cascade do |t|
    t.string "name"
    t.datetime "created_at", null: false
    t.datetime "updated_at", null: false
  end

  create_table "conditions", force: :cascade do |t|
    t.string "name"
    t.string "notes"
    t.integer "user_id"
    t.integer "medication_id"
    t.datetime "created_at", null: false
    t.datetime "updated_at", null: false
    t.index ["medication_id"], name: "index_conditions_on_medication_id"
    t.index ["user_id"], name: "index_conditions_on_user_id"
  end

  create_table "medications", force: :cascade do |t|
    t.string "name"
    t.integer "dosage"
    t.string "units"
    t.string "frequency"
    t.integer "times_per_day"
    t.date "start_date"
    t.integer "user_id"
    t.datetime "created_at", null: false
    t.datetime "updated_at", null: false
    t.integer "category_id"
    t.index ["user_id"], name: "index_medications_on_user_id"
  end

  create_table "users", force: :cascade do |t|
    t.string "username"
    t.string "email"
    t.string "password_digest"
    t.datetime "created_at", null: false
    t.datetime "updated_at", null: false
  end

end
```


It took some time for me to fully understand how all the concepts work together at a higher level, however this project allowed me to practice and make mistakes in order to really grasp how each part worked.  The use of Stack Overflow, Google, Rails documents, and referring previous lessons also helped tremendously. 
