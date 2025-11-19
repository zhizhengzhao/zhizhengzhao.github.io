The calculation is performed using the following code:

```python
# GPA calculation function
def calculate_gpa(grades_list):
    """
    Calculates the weighted GPA (Grade Point Average) for a list of courses.
    Excludes courses where the grade is 'W' (Withdrawal), '合格' (Pass), or GPA is not provided (None).
    
    Returns: (GPA_result, total_credits, total_weighted_points)
    """
    total_credits = 0
    weighted_grades = 0
    
    # Grades to exclude from GPA calculation
    non_gpa_grades = ['W', '合格', 'Pass']
    
    for course in grades_list:
        # Only include courses with a valid GPA (not None) and a quantifiable grade
        if course.get('gpa') is not None and course['grade'] not in non_gpa_grades:
            credits = course['credits']
            gpa = course['gpa']
            
            total_credits += credits
            weighted_grades += credits * gpa
            
    # Calculate GPA
    gpa_result = weighted_grades / total_credits if total_credits != 0 else 0
    
    return gpa_result, total_credits, weighted_grades

# --- Comprehensive Course Data (All years) ---
# Data includes 'year' for filtering Advanced GPA.
grades = [
    # Third Year (Year 3) - 2024-2025 Semester 2
    {'course': 'Advanced Oral English', 'credits': 2, 'grade': 90, 'gpa': 3.81, 'category': 'University Requirement', 'year': 3},
    {'course': 'Modern Chinese Educational Tradition and Its Changes', 'credits': 2, 'grade': 73.4, 'gpa': 2.67, 'category': 'General Elective', 'year': 3},
    {'course': 'Electrons and Photons', 'credits': 2, 'grade': 'W', 'gpa': None, 'category': 'Major Required', 'year': 3}, 
    {'course': 'Material Physics', 'credits': 3, 'grade': 89, 'gpa': 3.77, 'category': 'Elective', 'year': 3},
    {'course': 'An Introduction to Cloud Physics', 'credits': 2, 'grade': 92, 'gpa': 3.88, 'category': 'Elective', 'year': 3},
    {'course': 'Modern Physics Laboratory I', 'credits': 3, 'grade': 87, 'gpa': 3.68, 'category': 'Major Required', 'year': 3},
    {'course': 'Seminar for Quantum Mechanics', 'credits': 2, 'grade': 90, 'gpa': 3.81, 'category': 'Major Required', 'year': 3},

    # Third Year (Year 3) - 2024-2025 Semester 1
    {'course': 'Climate Change: The Scientific Basis for Global Warming', 'credits': 2, 'grade': 96, 'gpa': 3.97, 'category': 'Elective', 'year': 3},
    {'course': 'Quantum Mechanics (A)', 'credits': 4, 'grade': 'W', 'gpa': None, 'category': 'Major Required', 'year': 3}, 
    {'course': 'Jewish Civilization in a Global Context', 'credits': 2, 'grade': '合格', 'gpa': None, 'category': 'General Elective', 'year': 3},
    {'course': 'Physics and Artificial Intelligence', 'credits': 3, 'grade': '合格', 'gpa': None, 'category': 'Elective', 'year': 3},
    {'course': 'Mathematical Thought from Ancient to Modern Times', 'credits': 2, 'grade': 89, 'gpa': 3.77, 'category': 'General Elective', 'year': 3},
    {'course': 'Fundamentals of Electronic Circuits and Experiments (2)', 'credits': 2, 'grade': 88, 'gpa': 3.73, 'category': 'Major Required', 'year': 3},
    {'course': 'Introduction to Atmospheric Science', 'credits': 2, 'grade': 97, 'gpa': 3.98, 'category': 'Major Required', 'year': 3},
    {'course': 'Electrodynamics (A)', 'credits': 4, 'grade': 86, 'gpa': 3.63, 'category': 'Major Required', 'year': 3},

    # Second Year (Year 2) - 2023-2024 Semester 2
    {'course': 'An Introduction to Marxist Basic Theory', 'credits': 3, 'grade': 84, 'gpa': 3.52, 'category': 'University Requirement', 'year': 2},
    {'course': 'Shadowboxing', 'credits': 1, 'grade': 96.5, 'gpa': 3.98, 'category': 'University Requirement', 'year': 2},
    {'course': 'Seminar for Optics', 'credits': 2, 'grade': '合格', 'gpa': None, 'category': 'Major Required', 'year': 2},
    {'course': 'Fluid Mechanics', 'credits': 3, 'grade': 85, 'gpa': 3.58, 'category': 'Major Required', 'year': 2},
    {'course': 'Introduction to Seismology', 'credits': 2, 'grade': 98, 'gpa': 3.99, 'category': 'General Elective', 'year': 2},
    {'course': 'Electrodynamics (A) (W)', 'credits': 4, 'grade': 'W', 'gpa': None, 'category': 'Major Required', 'year': 2}, 
    {'course': 'Optics', 'credits': 4, 'grade': 89, 'gpa': 3.77, 'category': 'Major Required', 'year': 2},
    {'course': 'General Physics Lab (2)', 'credits': 3, 'grade': 84, 'gpa': 3.52, 'category': 'Major Required', 'year': 2},
    {'course': 'Methods of Mathematical Physics (2)', 'credits': 3, 'grade': 84, 'gpa': 3.52, 'category': 'Major Required', 'year': 2},

    # Second Year (Year 2) - 2023-2024 Semester 1
    {'course': 'General Physics Lab (1)', 'credits': 3, 'grade': 85, 'gpa': 3.58, 'category': 'Elective', 'year': 2},
    {'course': 'Fundamentals of Electronic Circuits and Experiments (1)', 'credits': 3, 'grade': 83, 'gpa': 3.46, 'category': 'Elective', 'year': 2},
    {'course': 'Theoretical Mechanics (A)', 'credits': 4, 'grade': 71, 'gpa': 2.42, 'category': 'Major Required', 'year': 2},
    {'course': 'Equilibrium Statistical Physics', 'credits': 4, 'grade': 74, 'gpa': 2.73, 'category': 'Major Required', 'year': 2},
    {'course': 'Methods of Mathematical Physics (1)', 'credits': 3, 'grade': 82, 'gpa': 3.39, 'category': 'Major Required', 'year': 2},
    {'course': 'Electrodynamics (A) (W-Elective)', 'credits': 4, 'grade': 'W', 'gpa': None, 'category': 'Elective', 'year': 2}, 
    {'course': 'Physics Application and Practice', 'credits': 1, 'grade': '合格', 'gpa': None, 'category': 'Elective', 'year': 2},
    {'course': 'A Survey of Mao Tsetung Thoughts...', 'credits': 3, 'grade': 93, 'gpa': 3.91, 'category': 'University Requirement', 'year': 2},

    # First Year (Year 1) - 2022-2023 Semester 2
    {'course': 'Basketball', 'credits': 1, 'grade': 93, 'gpa': 3.91, 'category': 'University Requirement', 'year': 1},
    {'course': 'Introduction to Xi Jinping Thought...', 'credits': 3, 'grade': 82, 'gpa': 3.39, 'category': 'University Requirement', 'year': 1},
    {'course': 'Advanced Mathematics A (no. 2)', 'credits': 5, 'grade': 81, 'gpa': 3.32, 'category': 'Major Required', 'year': 1},
    {'course': 'Data Structure and Algorithm (B)', 'credits': 3, 'grade': 89, 'gpa': 3.77, 'category': 'University Requirement', 'year': 1},
    {'course': 'English Reading', 'credits': 2, 'grade': 86, 'gpa': 3.63, 'category': 'University Requirement', 'year': 1},
    {'course': 'Thermal Physics', 'credits': 3, 'grade': 90, 'gpa': 3.81, 'category': 'Major Required', 'year': 1},
    {'course': 'Social practice and service learning, Part II', 'credits': 1, 'grade': '合格', 'gpa': None, 'category': 'University Requirement', 'year': 1},
    {'course': 'Electromagnetism', 'credits': 4, 'grade': 83, 'gpa': 3.46, 'category': 'Major Required', 'year': 1},
    {'course': 'An Introduction to Ideological & Moral Culture and Laws', 'credits': 3, 'grade': 78, 'gpa': 3.09, 'category': 'University Requirement', 'year': 1},
    
    # First Year (Year 1) - 2022-2023 Semester 1
    {'course': 'Outline of Chinese Modern History', 'credits': 3, 'grade': '合格', 'gpa': None, 'category': 'University Requirement', 'year': 1},
    {'course': 'Mechanics', 'credits': 4, 'grade': 82, 'gpa': 3.39, 'category': 'Elective', 'year': 1},
    {'course': 'English Listening and Speaking', 'credits': 2, 'grade': '合格', 'gpa': None, 'category': 'University Requirement', 'year': 1},
    {'course': 'Events and Policies', 'credits': 2, 'grade': '合格', 'gpa': None, 'category': 'University Requirement', 'year': 1},
    {'course': 'Introduction to Computation (B)', 'credits': 3, 'grade': 90, 'gpa': 3.81, 'category': 'University Requirement', 'year': 1},
    {'course': 'Military Theory', 'credits': 2, 'grade': '合格', 'gpa': None, 'category': 'University Requirement', 'year': 1},
    {'course': 'Advanced Mathematics A (no. 1)', 'credits': 5, 'grade': '合格', 'gpa': None, 'category': 'Major Required', 'year': 1},
    {'course': 'Linear Algebra (B)', 'credits': 4, 'grade': 78, 'gpa': 3.09, 'category': 'Major Required', 'year': 1},
    {'course': 'Social practice and service learning, Part I', 'credits': 1, 'grade': '合格', 'gpa': None, 'category': 'University Requirement', 'year': 1},
    {'course': 'Lectures on The Frontiers of Modern Physics (I)', 'credits': 2, 'grade': '合格', 'gpa': None, 'category': 'Elective', 'year': 1}
]

# --- 1. Cumulative GPA Calculation (All years) ---
cumulative_gpa, cumulative_credits, cumulative_weighted_gpa = calculate_gpa(grades)

# --- 2. Advanced GPA Calculation (Year >= 3) ---
advanced_grades = [grade for grade in grades if grade['year'] >= 3]
advanced_gpa, advanced_credits, advanced_weighted_gpa = calculate_gpa(advanced_grades)

# --- Output Results ---
print("--- GPA Calculation Results for Worksheet Submission ---")
print("\n### 1. Undergraduate Cumulative GPA ###")
print(f"**Calculated Cumulative GPA (0.00 to 4.00):** {cumulative_gpa:.2f}")

print("\n### 2. Advanced Undergraduate GPA (Courses completed after the second year) ###")
print(f"**Calculated Advanced GPA (0.00 to 4.00):** {advanced_gpa:.2f}")
```

The result is:

```python
### 1. Undergraduate Cumulative GPA ###
**Calculated Cumulative GPA (0.00 to 4.00):** 3.50

### 2. Advanced Undergraduate GPA (Courses completed after the second year) ###
**Calculated Advanced GPA (0.00 to 4.00):** 3.70
```

