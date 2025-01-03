Background:
Program Overview:
- Total Lessons: 24
- Session Duration: 1 hour per session
- Meeting Frequency: Weekly check-ins with mentors via Zoom
- Program Duration: Approximately 6 months
- Class Size: One teacher per eight students (1:8 ratio)

Program Structure:
1. Quick View of Program Modules:
- Lessons and Topics: Each lesson covers specific topics essential to the program.
- Objectives and Goals: Clearly defined objectives for each lesson provided in the slides.
- Class Activities: Activities to be completed during the class, including:
* Worksheets
* Exercises
* Pop quizzes
* Exit tickets
* Other interactive tasks

2. Learning and Teaching Materials:
- Lesson Guidelines: Detailed instructions and expectations for each lesson.
- Slides: Presentation materials to guide the lesson.
- Activity Links: URLs to activities used during the class session.
- Submission Links: URLs where students submit their work before the session ends.
- Sample Answers: Provided exclusively for teachers to reference.

Student Management:
- Breakout Room Management: Utilization of a single Zoom account with up to 20 breakout rooms to facilitate group activities and discussions.
- Attendance Policy: Attendance is recorded based on lesson completion dates. There are no make-up classes; if a student misses a session, they proceed to the next one.

Activity Management:
- Real-Time Activities: Live teaching sessions using prepared materials accessible through a learning dashboard in a wiki library format.
- Submissions: Assignments and activities are submitted via third-party tools such as Google Forms and Quizzes.
- Collaboration Tools: Use of platforms like Colab, Glitch, and Scratch for coding exercises and collaborative projects.

Assessment:
- Assessment Methods: Simple assessments including pop quizzes and project submissions through links (e.g., Colab, Glitch).
- Progress Measurement: Progress is tracked based on attendance, assignment submissions, and mutual ratings between students and teachers.
- Grading System: While not mandatory, a grading system is a desirable feature. Academic transcripts are generated to record quiz scores, assignments, and other assessments.

Teacher Support:
- Training Sessions: Teachers receive training during their orientation period.
- Communication Tools: Slack and WhatsApp are used for effective communication among teachers.
- Teacher Substitutions: Managed manually by identifying available teachers based on time slots, experience, teaching capabilities, and willingness to substitute.

Additional Details:
- Use of External Tools: The program frequently incorporates third-party platforms for enhanced learning experiences, especially in coding lessons.
- Cost-Efficiency Measures: To save costs, a single Zoom account is optimized with multiple breakout rooms rather than individual accounts for each class.
- Student-Teacher Interaction: Emphasis on live interaction during sessions to maximize engagement and understanding.
- Feedback Mechanism: Both students and teachers provide ratings for each other to facilitate continuous improvement.
- No Make-Up Sessions: The program’s structure does not accommodate make-up classes; students are encouraged to attend all sessions to ensure consistent progress.

Summary:
This program is designed to provide a comprehensive learning experience over six months, with a focus on interactive and engaging teaching methods. By leveraging live sessions, breakout rooms, and various online tools, students receive a well-rounded education in their chosen subject. The program values cost-efficiency, effective student management, and continuous assessment to track and support student progress. Teachers are well-supported through training and communication platforms, ensuring they can deliver high-quality education throughout the program.






## Project overview
A comprehensive platform for managing B-C gig teachers, focusing on curriculum delivery, session management, and progress tracking. The platform enables teachers to host sessions, conduct workshops, and manage weekly classes while automating payment calculations based on various factors.

## Core functionalities
### 1. Resources Dashboard
#### Purpose
Centralized system for managing and accessing teaching materials, documentation, and resources.

#### Key Features
- Resource categorization and filtering
- List and grid view options
- Preview functionality for different file types
- Material status tracking
- Download and usage analytics

## Core Components
### 1. Resources Dashboard
#### Purpose
Centralized system for managing and accessing teaching materials, documentation, and resources.

#### Key Features
- Resource categorization and filtering
- List and grid view options
- Preview functionality for different file types
- Material status tracking
- Download and usage analytics


## Relevant Doc

## Current file structure

## Rules


































# Project overview
xxxx

# Feature requirements
- xxxx
- xxx

# Relevant docs
## How to use replicate emoji generator model

# Current File structure
##Help me generate the file structure in ASCII version

# Rules
- All new components should go in /components and be named like example-component.tsx unless otherwise specified.
- All new pages go in /app.

# Tech stack
- We will use Next.js, Supabase, Clerk

# Tables & buckets already created
Supabase storage Bucket: "emojis"

```sql
TABLE emojis (
  id BIGINT PRIMARY KEY GENERATED BY DEFAULT AS IDENTITY,
  image_url TEXT NOT NULL,
  prompt TEXT NOT NULL,
  likes_count NUMERIC DEFAULT 0,
  creator_user_id TEXT NOT NULL,
  created_at TIMESTAMP WITH TIME ZONE DEFAULT NOW()
);

TABLE profiles (
  user_id TEXT PRIMARY KEY,
  credits INTEGER DEFAULT 3 NOT NULL,
  tier TEXT NOT NULL DEFAULT 'free' CHECK (tier IN ('free', 'pro')),
  stripe_customer_id TEXT,
  stripe_subscription_id TEXT,
  created_at TIMESTAMP WITH TIME ZONE DEFAULT CURRENT_TIMESTAMP NOT NULL,
  updated_at TIMESTAMP WITH TIME ZONE DEFAULT CURRENT_TIMESTAMP NOT NULL
);



# Requirements

1. Create user-to-user table
   - After a user signs in via Clerk, we should get the `userId` from Clerk and check if this `userId` exists in the `profiles` table, matching "user_id".
   - If the user doesn't exist, then create a user in the `profiles` table.
   - If the user exists already, then proceed and pass on `user_id` to functions like generating emojis.

2. Upload emoji to "emojis" Supabase storage bucket
   - When a user generates an emoji, upload the emoji image file returned from Replicate to the Supabase "emojis" storage bucket.
   - Add the image URL to the `emojis` data table as `image_url` and `creator_user_id` to be the actual `user_id`.

3. Display all images in emoji grid
   - Emoji grid should fetch and display all images from the `emojis` data table.
   - When a new emoji is generated, the emoji grid should be updated automatically to add the new emoji to the grid.

4. Likes interaction
   - When a user clicks on the "like" button, the `num_likes` should increase on the `emojis` table.
   - When a user unclicks the "like" button, the `num_likes` should decrease on the `emojis` table.



# Documentations

## Example of uploading files to Supabase storage
```javascript
import { createClient } from '@supabase/supabase-js';

// Create Supabase client
const supabase = createClient('your_project_url', 'your_supabase_api_key');

// Upload file using standard upload
async function uploadFile(file) {
  const { data, error } = await supabase.storage.from('bucket_name').upload('file_path', file);
  if (error) {
    // Handle error
  } else {
    // Handle success
  }
}







Problem solving
- I found this, what would be the root course, let's think step by step 





V0.dev
- I'm building a Reddit analytics platform, above is the home page displaying all the subreddits available; 
- Please keep the functionalities exactly like above, but make UI looks a ton better; 
- (Remember ONLY change UI, do not change functionalities or variables).


Terminal Example:
1. tree -L 3 -I 'node_modules|.git'


Prompt Example: 
Help me add details to the original PRD that give clear alignment to developers who will implement the project:
- Don't create actual code, just the PRD.
- Include file structure into the doc.
- Include all documentation provided (with both example code & responses, those are important context). 

Help me identify the root cause & resolve this issue;
Let’s think step by step

@reddit.ts, the categorizePost function is not implemented correctly, it has to be based on the documentation we provided in @instructions.md (202~268), please refactor the code.

@Codebase

I have the project built based on @instructions.md but currently, we need to fetch Reddit data & call OpenAI API every time someone opens the subreddit page, which is not optimal;

I want a backend engineer to connect it to Supabase and save Reddit posts data & AI analysis data to Supabase; and only refetch data if the last update time is older than 24 hrs ago.

Help me generate a detailed document that can help backend developers understand this project structure, and what core parts to build for Supabase integration that is compatible with this project structure (no need to include actual code examples, just need a design doc).

And output the final doc in markdown called "project_details.md".


@Codebase

I have the project built based on @instructions.md, but currently, we need to fetch Reddit data & call OpenAI API every time someone opens the subreddit page, which is not optimal;

I want a backend engineer to connect it to Supabase and save Reddit posts data & AI analysis data to Supabase; and only refetch data if the last update time is older than 24 hrs ago.

Help me generate a detailed document that can help backend developers understand this project structure, what core parts to build for Supabase integration compatible with this project structure, and what databases should we create & schema (no need to include actual code examples, just need a design doc).

Let's think step by step



Give me the SQL command to create all tables in Supabase directly. 


We need to implement Supabase integration for this current project based on instruction here.



