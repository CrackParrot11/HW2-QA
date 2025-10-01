# sQaaS™ - Student Question and Answer System

A comprehensive JavaFX desktop application for students to ask questions, provide answers, and collaborate on learning. Built with user authentication, role-based access control, and intelligent input validation.


Mermaid diagram links:

Class Diagram:
https://www.mermaidchart.com/d/d9f97e92-a79c-4f25-8ccf-dce67f56c6b7


Sequence Diagram:
https://www.mermaidchart.com/d/d224f96d-2e15-484c-8dd6-d8d7dd2e99b2

### Core Functionality
- **User Authentication System**: Secure login with username/password validation
- **Role-Based Access Control**: Admin and student roles with different permissions
- **Question & Answer System**: 
  - Ask questions (5-100 char title, 10-500 char content)
  - Provide answers (5-500 characters)
  - Search for similar questions
  - Mark questions as resolved
  - Close questions when satisfied
  - Upvote helpful answers
  - Edit and delete your own content

### Advanced Features
- **Real-Time Input Validation**:
  - Character counters with visual feedback
  - Spell checking with auto-correction
  - Grammar checking (capitalization, punctuation, etc.)
  - Warning system (blocking errors vs. suggestions)
- **Admin Features**:
  - User management dashboard
  - Generate invitation codes
  - Reset user passwords (One-Time Password system)
  - Manage user roles
- **Unread Answer Tracking**: See how many new answers you have
- **Answer Sorting**: Answers sorted by upvotes (most helpful first)

---

## 🔧 Prerequisites

Before you begin, ensure you have the following installed:

1. **Java Development Kit (JDK) 11 or higher**
   - Download from: [Oracle JDK](https://www.oracle.com/java/technologies/downloads/) or [OpenJDK](https://openjdk.org/)
   - Verify installation: `java -version`

2. **Eclipse IDE** (or IntelliJ IDEA)
   - Eclipse Download: [https://www.eclipse.org/downloads/](https://www.eclipse.org/downloads/)
   - Recommended: Eclipse IDE for Java Developers

3. **JavaFX SDK** (if not included in your JDK)
   - Download from: [https://gluonhq.com/products/javafx/](https://gluonhq.com/products/javafx/)
   - Extract to a known location (e.g., `C:\javafx-sdk-21` or `/usr/lib/javafx`)

---

## 📦 Dependencies

### Required Libraries

1. **H2 Database Engine** (Version 2.1.214 or compatible)
   - Download JAR: [https://www.h2database.com/](https://www.h2database.com/)
   - File needed: `h2-*.jar`

2. **JavaFX Libraries** (Version 11 or higher)
   - Already included if using JDK 11+ from Oracle
   - If separate SDK: Requires `javafx.controls`, `javafx.fxml`, `javafx.graphics`

3. **JUnit 5** (for testing)
   - Usually bundled with Eclipse
   - If not: Download from [https://junit.org/junit5/](https://junit.org/junit5/)

---

## 🚀 Installation

### Step 1: Clone or Download the Repository

```bash
git clone https://github.com/yourusername/sQaaS-System.git
cd sQaaS-System
```

Or download as ZIP and extract.

### Step 2: Set Up Eclipse Project

1. **Open Eclipse**
2. **Import the Project**:
   - `File` → `Import` → `General` → `Existing Projects into Workspace`
   - Select the downloaded repository folder
   - Click `Finish`

### Step 3: Add Dependencies to Build Path

#### Add H2 Database JAR:
1. Download `h2-*.jar` from [H2 Database](https://www.h2database.com/)
2. In Eclipse:
   - Right-click project → `Properties`
   - Select `Java Build Path` → `Libraries` tab
   - Click `Add External JARs...`
   - Navigate to and select `h2-*.jar`
   - Click `Apply and Close`

#### Configure JavaFX (if needed):
1. Right-click project → `Properties`
2. `Java Build Path` → `Libraries` → `Add Library` → `User Library`
3. Click `User Libraries...` → `New...` → Name it "JavaFX"
4. Select JavaFX → `Add External JARs...`
5. Navigate to your JavaFX SDK `lib` folder
6. Select all `.jar` files in the `lib` folder
7. Click `Apply and Close`

#### Add JUnit 5:
1. Right-click project → `Properties`
2. `Java Build Path` → `Libraries` → `Add Library`
3. Select `JUnit` → `Next`
4. Choose `JUnit 5` → `Finish`

### Step 4: Configure VM Arguments (JavaFX only)

If using JavaFX SDK separately:

1. `Run` → `Run Configurations...`
2. Select your main class (`StartCSE360`)
3. Go to `Arguments` tab
4. In `VM arguments`, add:

```
--module-path "/path/to/javafx-sdk/lib" --add-modules javafx.controls,javafx.fxml
```

**Example for Windows:**
```
--module-path "C:\javafx-sdk-21\lib" --add-modules javafx.controls,javafx.fxml
```

**Example for macOS/Linux:**
```
--module-path "/usr/lib/javafx/lib" --add-modules javafx.controls,javafx.fxml
```

---

## ▶️ Running the Application

### From Eclipse:

1. **Locate the main class**: `src/application/StartCSE360.java`
2. **Right-click** on `StartCSE360.java`
3. Select **`Run As`** → **`Java Application`**

### First Time Setup:

When you run the application for the first time:
1. You'll see a "First Run" screen
2. Click **"Continue"** to set up the first admin account
3. Fill in:
   - Username (4-20 characters)
   - Password (6+ characters: upper, lower, digit, special char)
   - Email
   - Name
4. Click **"Continue as Admin"**

### Subsequent Runs:

- Login with your username and password
- **Admin users**: Access Admin Panel or Q&A System
- **Regular users**: Access Q&A System and profile management

---

## 🔄 Integration with FoundationCode

If you're a student integrating this project with the instructor's **FoundationCode** repository:

### Quick Integration Steps:

1. **Download the instructor's FoundationCode** (if you haven't already)
2. **Copy ONLY the `src` folder** from this project
3. **Paste into the FoundationCode project**, replacing/merging:
   ```
   FoundationCode/
   ├── src/
   │   ├── application/          ← Copy all files from this project
   │   └── databasePart1/        ← Copy all files from this project
   ```

4. **Ensure Dependencies are Set**:
   - H2 Database JAR must be in the build path
   - JUnit 5 must be configured
   - JavaFX must be configured (if needed)

5. **Run `StartCSE360.java`** from the FoundationCode project

### What Gets Transferred:
