# Database Table Description

## Student
Students enrolled for this course.
- `studentId` - [**PK**][*string*] - ID of the student.
- `class` - [*small integer*] - The class the student is in (Day / In Service).
- `name` - [*string*] - The name of the student.
- `email` - [*string*] - The email of the student.

## Presenter
In-service students that need to present in class.
- `presenterId` - [**PK**][**FK** (`studentId`)][*string*] - ID of the student.
- `week` - [*string*] - The week the presenter needs to present.
- `presentOrder` - [*integer*] - The order of presentation for the week.
- `grade` - [*double*] - The grade for the presenter of the week.

## Reviewer
Daytime students that need to review in class.
- `reviewerId` - [**PK**][**FK**(`studentId`)][*string*] - ID of the student.
- `week` - [**PK**][*string*] - The week of the event.
- `supportA` - [*double*] - The support score for the reviewer's A (best) vote.
- `supportC` - [*double*] - The support score for the reviewer's C (worst) vote.
- `grade` - [*double*] - The grade for the reviewer of the week.

## FormSubmission
The submission record for a reviewer in a week.
- `reviewerId` - [**PK**][**FK**(`studentId`)][*string*] - The reviewer submitting this form.
- `week` - [**PK**][*integer*] - The week of the record.
- `bestPresenterId` - [*string*] - The presenter the reviewer thinks performs the best.
- `worstPresenterId` - [*string*] - The presenter the reviewer thinks performs the worst.
- `comment` - [*string*] - The comment of the reviewer.
- `submitDateTime` - [*string*] - The time when the form is submitted.