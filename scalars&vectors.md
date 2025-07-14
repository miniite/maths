

# Introduction to Scalars and Vectors

- This video continues the linear algebra series, focusing on scalars and vectors.
- Emphasis on their applications in data science, with examples tailored to computer science and data analytics.
- Scalars and vectors are used across fields like physics and mathematics, but the focus here is on data science applications.

## Definition of Scalars

- A scalar is a single numerical value representing magnitude or quantity without direction.
### Examples
- **Car Speed**: 45 km/h represents magnitude without direction.
- **Temperature**: 25°C is a scalar, indicating magnitude without directional component.
### Applications in Data Science
- **Dataset Metrics**: Scalars represent single values like the count of records (e.g., 5 records in a dataset) or the average of a feature (e.g., average age).
- **Simple Linear Regression**: In the equation \( y = mx + c \), the intercept \( c \) is a scalar, a single numerical value, while the slope \( m \) depends on data points and is not considered a scalar.

## Definition of Vectors
### Overview
- **Physics Definition**: A vector is a numerical value with both magnitude and direction (e.g., car speed of 45 km/h moving east).
- **Data Science Definition**: A vector is an ordered list of numbers representing a point in space or a quantity with magnitude and direction.
### Examples
- **Student Marks Dataset**: Features like IQ (e.g., 90) and study hours (e.g., 3) form a vector (90, 3), representing a data point.
- **Weight Over Time**: Monthly weights (e.g., 70 kg, 72 kg, 75 kg, 73 kg) form a four-dimensional vector.
- **Coordinate System Representation**: A vector like (1, 2) in a 2D coordinate system represents a point with x=1 and y=2, with magnitude calculated using the Pythagorean theorem (e.g., \(\sqrt{1^2 + 2^2} = \sqrt{5}\)).
### Unit Vectors
- A unit vector has a magnitude of 1 (e.g., \(\hat{i}\) for x-axis, \(\hat{j}\) for y-axis).
- Example: Vector (3, 3) can be expressed as \( 3\hat{i} + 3\hat{j} \), indicating movement of 3 units along x and y axes.
### Properties
- Vectors in data science represent collections of values in various dimensions (e.g., 2D, 3D, or higher), not necessarily physical directions.
- Vectors maintain the same direction and magnitude regardless of the origin in a coordinate system.

## Applications of Vectors in Data Science
### Data Representation
- Each record in a dataset (e.g., IQ and study hours) is represented as a vector (e.g., (90, 3)).
- Enables visualization of data points in a coordinate system (e.g., plotting IQ vs. study hours).
### Model Training
- In machine learning (e.g., logistic regression for classification), vectors represent data points to train models.
- Example: In a student dataset, vectors (e.g., (90, 2) for fail, (100, 3) for pass) help models create decision boundaries (e.g., a linear line \( y = mx + c \)) to classify outcomes.
### High-Dimensional Data
- Linear algebra supports vectors in high dimensions (e.g., 5000 features), allowing complex data representation and manipulation, with techniques to reduce dimensions later.

## Applications in Other Fields
### Gaming Industry
- Vectors model motion and collisions (e.g., in GTA, a car moving at 200 km/h in a direction or a boat moving against waves at 60 km/h).
- Used to calculate outcomes like car crashes or boat jumps based on vector interactions.
### Coordinate System Movement
- Example: Moving a box in a coordinate system using vectors (e.g., from (0, 0) to (3, 3)) illustrates how vectors represent direction and magnitude of movement.

## Series Objective
### Overview
- To explain scalars and vectors with data science examples, focusing on their role in representing and manipulating data.
- Future videos will cover vector addition, multiplication, and their significance in coordinate systems.
- Aims to demonstrate how linear algebra handles high-dimensional data and supports machine learning and deep learning applications.

