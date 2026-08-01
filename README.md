# Computer Graphics CSC317/CSC2504 _Fall 2026_

![_image courtesy Tim Jeruzalski_](images/bunny-rigid-body.gif)

- [Course Overview](#course-overview)
- [Recommended Textbook](#recommended-textbook)
- [Lecture Schedule](#lecture-schedule)
- [Assignments](#assignments)
- [Lateness Policy](#lateness-policy)
- [Grading](#grading)
- [Academic Honesty (required reading)](#academic-honesty)

## Sections

|                | **LEC 0101/2001** | **LEC 0201** |
|----------------|--------------|--------------|
| Instructor     | Prof. [Karan Singh](https://www.dgp.toronto.edu/~karan/) | Jonathan Panuelos |
| Contact        | <karan@dgp.toronto.edu> | <jonathan.panuelos@mail.utoronto.ca> |
| Lecture        | Tue 13:00–15:00 MS2170 | Tue 15:00–17:00 MS2172 |
| Lecture (cont.)| Thu 13:00–14:00 UC140  | Thu 15:00–16:00 BR200 |
| Office Hours   | TBD | TBD |

*_You can attend any office hours that fits your schedule_

## TAs

TBD

<csc317tas@cs.toronto.edu>

## Links

- [MarkUs](https://markus.teach.cs.toronto.edu/markus)

**Use Assignment GitHub issue pages for questions/discussion**

## Programming Resources

Assignments this term are written in **Python**. The course stack is
intentionally lightweight — four libraries and nothing else.

[Python 3 Tutorial](https://docs.python.org/3/tutorial/)

[NumPy User Guide](https://numpy.org/doc/stable/user/)

[SciPy Documentation](https://docs.scipy.org/doc/scipy/)

[Pillow (PIL) Handbook](https://pillow.readthedocs.io/en/stable/handbook/index.html)

[Polyscope (3D viewer)](https://polyscope.run/py/)

[The Matrix Cookbook](https://www.math.uwaterloo.ca/~hwolkowi/matrixcookbook.pdf)

## Getting Set Up

All six assignments live in a single repository. Clone it once, run the
init script once, and then activate the environment in each new shell.

```bash
./init.sh                     # macOS / Linux — creates ./venv and installs deps
# .\init.ps1                  # Windows (PowerShell)
```

> **Windows note:** if script execution is disabled, run
> `powershell -ExecutionPolicy Bypass -File init.ps1`

```bash
source venv/bin/activate            # macOS / Linux
# .\venv\Scripts\Activate.ps1       # Windows
```

To work on an assignment:

```bash
cd Assignments/A1-Raster_Images
python main.py                # run the demo harness end-to-end
python run_tests.py           # self-check: reports "Validated X/Y"
```

You edit **only** the files in each assignment's `src/` directory. Every stub
documents its inputs, outputs, and algorithm. The `tests/` directory and the
shared `cgcommon` package must not be modified.

## Course Overview

This course introduces the basic concepts and algorithms of computer graphics.
It covers the basic methods needed to model and render 3D objects, including
much of the following: graphics displays, basic optics, line drawing, affine and
perspective transformations, windows and viewports, clipping, visibility,
illumination and reflectance models, radiometry, energy transfer models,
parametric representations, curves and surfaces, texture mapping, graphics
hardware, ray tracing, graphics toolkits, animation systems.

**Prerequisites:** Python Programming, Linear Algebra, Calculus, Numerical
Methods.

The student is expected to read background material on the hardware and local
software, and should be comfortable with elementary linear algebra, geometry,
and vector calculus. It is also assumed that the student is comfortable
programming in basic Python, including working with NumPy arrays.

**_(Strongly)_ Recommended preparation:** Multivariable Calculus

## Recommended Textbook

![The Book.](https://www.cs.cornell.edu/~srm/fcg4/K22616_cover-300.jpg)

This class involves  **_required reading_** from:

[_Fundamentals of Computer Graphics, Fourth
Edition_](https://www.cs.cornell.edu/~srm/fcg4/), Steve Marschner, Peter Shirley,
et al. 2015.

Digital e-book are available at [CRC
Press](https://www.crcpress.com/Fundamentals-of-Computer-Graphics-Fourth-Edition/Marschner-Shirley/p/book/9781482229394).

## Lecture Schedule

Below is the schedule for the course with each row of the table showing the week beginning with Sunday.

- Tuesdays: Lecture (2h)
- Wednesdays: Quiz release + due dates (online, due the same week)
- Thursdays: Lecture (1h) — and the three **Tests**
- Fridays: Assignment due dates **(11:59pm)** on Markus.

| Week | Sunday  | Mon              | Tue (Lecture, 2h)               | Wed (Quiz Release+Due) | Thu (Lecture, 1h / Test) | Fri (Assignment Due) |
|------|:--------|------------------|---------------------------------|------------------------|--------------------------|----------------------|
| 1    | Sep 6   | **Labour Day**   | Introduction + Rasterization    |                        | Introduction + Rasterization | |
| 2    | Sep 13  |                  | Ray Casting                     | q1 released + due      | Ray Casting              | a1 + oh1             |
| 3    | Sep 20  |                  | Ray Tracing                     | q2 released + due      | Ray Tracing              |                      |
| 4    | Sep 27  |                  | Ray Tracing                     |                        | **Test 1 (Wk 1–4)**      |                      |
| 5    | Oct 4   |                  | BVH                             |                        | BVH                      | a2 + oh2             |
| 6    | Oct 11  | **Thanksgiving** | Meshes                          | q3 released + due      | Meshes                   |                      |
| 7    | Oct 18  |                  | Shaders                         | q4 released + due      | Shaders                  | a3 + oh3             |
| 8    | Oct 25  | **Reading Week** | **Reading Week**                | **Reading Week**       | **Reading Week**         | **Reading Week**     |
| 9    | Nov 1   |                  | Shaders                         |                        | **Test 2 (BVH–Shaders)** |                      |
| 10   | Nov 8   |                  | Kinematics                      |                        | Kinematics               | a4 + oh4             |
| 11   | Nov 15  |                  | Springs (**Drop Day** Tue Nov 17) | q5 released + due    | Springs                  |                      |
| 12   | Nov 22  |                  | Guest Lecture / New Work        |                        | Guest Lecture / New Work | a5 + oh5             |
| 13   | Nov 29  |                  | Showcase + Current Research     |                        | **Test 3 (Wk 9–11)**     |                      |
| 14   | Dec 6   |                  | _no class_ — showcase due Tue Dec 8 |                    | _no class_               | a6 + oh6             |

You can find a series of short videos cut up by lectures and topics voicing over the lecture slides [here](https://drive.google.com/drive/folders/1cWDOSB-DHepfBlj_vdDsf9mU9sLP8sem?usp=sharing).

## Grading

| % | Item |
| ----: | :-------------- |
|5 | Assignment 1 — Raster Images
|40| Assignments 2–6 (8% each)
|10| 5 Quizzes (Online, 2% each)
|15| Test 1 (Weeks 1–4: Rasterization, Ray Casting, Ray Tracing)
|15| Test 2 (Weeks 5–8: BVH, Meshes, Shaders)
|15| Test 3 (Weeks 9–11: Kinematics, Mass-Springs)

Plus up to **5% extra credit** for the [creative showcase](showcase.md).

## Assignments

**Note: All assignments are available immediately. BUT we are only covering one assignment at a time. While  you are welcome to look ahead, future assignments
have not been debugged and we will not answer questions about them at office hours until we cover them in lecture**

| Assignment | Topics |
| ---------- | ------ |
| Assignment 1: Raster Images | Image representation: color, grayscale, mosaics/demosaicing, HSV, compositing. |
| Assignment 2: Ray Tracing | Ray casting **and** ray tracing: intersections, a perspective camera, Blinn-Phong shading, shadows, mirror reflections. |
| Assignment 3: Bounding Volume Hierarchy | Spatial acceleration: axis-aligned bounding-box trees for fast ray-mesh, nearest-neighbor, and broad-phase intersection queries. |
| Assignment 4: Meshes and Shaders | Triangle/quad meshes, normals, Catmull-Clark subdivision, OBJ I/O, then NumPy "software shaders": transforms, Blinn-Phong, procedural noise, bump mapping. |
| Assignment 5: Kinematics | Skeletal animation: forward kinematics, linear blend skinning, keyframe interpolation, and inverse kinematics by projected gradient descent. |
| Assignment 6: Mass-Spring Systems | Physically based simulation: the local-global "fast mass-springs" solver, dense and sparse. |
| [Showcase](showcase.md) | Optional creative piece for up to 5% extra credit. |

_Assignment repository links will be posted here once each assignment goes
live._

Assignments will be due on their respective Friday due dates at **11:59pm**.

### Lateness Policy

Every student is given eight (8) grace tokens which are automatically applied for assignments on Markus starting at midnight on the due date. Each grace token will provide an additional 12 hours period to submit your assignment without penalty.  Grace tokens do not replenish, so use them wisely.  Weekends count as late days.  You cannot choose which assignments to apply your grace tokens.  Once you run out of grace tokens, any **late assignments will be counted as 0 marks**.

For example, say you have 8 grace tokens.  If a1 is due on Friday 11:59pm and you submit your assignment on Sunday 4pm, you will have used 4 grace tokens: Friday 11:59pm -> Saturday 11:59am (1gt) -> Saturday 11:59pm (1gt) -> Sunday 11:59am (1gt) -> Sunday 11:59pm (1gt).  You will now have 4 grace tokens left for other assignments.

## Quizzes

There will be 5 online quizzes available through Quercus, worth 2% each. Each quiz goes live on the Wednesday shown in the schedule above, after the respective topics have been covered in class, and is **due that same week**.

You will only have 1 attempt to complete the quiz.

[Academic Honesty (required reading)](#academic-honesty)

![_image courtesy Gavin Barill_](images/gavin-barill-snowglobe.jpg)

### Academic Honesty

Academic honesty is a very serious matter and can result in very serious
consequences. Note that academic offences may be discovered and handled
retroactively, even after the semester in which the course was taken for credit.
This is a challenging class aimed at teaching you the fundamentals of computer
graphics. You won't learn much if you cheat but you might get a good grade if you
get away with it. If all you want is a good grade take an easier class where you
won't have to cheat!

For purposes of this class, academic dishonesty is defined as:

- Any attempt to pass off work on a test, quiz or assignment that didn't come straight out of your
  own head.
- Any collaboration on written or programming assignments (its ok to share ideas
  on programming assignments but the code MUST be your own) in which the
  collaborating parties don't clearly and prominently explain exactly who did
  what, at turn-in time.
- Any activity that has the effect of significantly impairing the ability of
  another student to learn. Examples here might include destroying the work of
  others, interfering with their access to resources (e.g., digital cameras), or
  deliberately providing them with misleading information.

### Email & Bulletin Board Traffic

- Please use the TA Email List for all communications except for things that require a Professors dedicated attention.
- Use github issue pages on assignment pages for questions
- Do NOT broadcast pieces of your code or answers to written assignments to the
  github issues. Specific or general implementation questions whose answer
  would benefit all students in the class are appropriate. However: the bulletin
  board is NO replacement for lecture and office hours. Those should be the main
  forum for asking/answering questions of this sort.
- Questions of the form "I cannot find the problem with my code; here it is, can
  you help me" are unlikely to be replied, so don't count on it. If you have a
  question with code, take it to the TA office hours.

