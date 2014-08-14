LSU GradeBook Patches
=================
###All patches are for Moodle 2.7
#How to apply
From your Moodle wwwroot folder:
```
patch -p1 < /path/to/patch.patch
```
#Patches for individual LSU gradebook features.
1. anonymous_grades.patch
   1. Requires quick edit.
   1. Allows for truly anonymous grading of manual items within Moodle.
      1. Graded items can only be adjusted by an administratively predefined adjustment value.
      1. Requires students be assigned anonymous identifiers as optional profile fields.
   * LSU settings
      * anon grading checked
      * 'create anonymous field' and assign anon numbers to users
      * set 'anonymous' as the anon field 
      * anonymous categories set to anything
      * in 'Grade Item Settings' , check 'manual item recompute'
  1. LSU testing steps
      1. confirm that when creating a new grate item, that the 'anonymous item' check box appears when enabled in gradebook settings
      1. create an anonymous grade item
      1. in the grader report, verify that the anonymous grade is not editable
      1. in QuickEdit, verify that an 'Anonymous Item' select is present.
      2. ensure that the anonymous adjustment value is reflected in the grader report
      3. test unlimited grades
         4. if a grade item is in an anon category and unlimited grades are turned on
         5. verify that you cannot exeed the max grade,despite the 'unlimited' setting
6. better_letters.patch
   1. Fixes hard-coded 2 decimal rounding bug.
   1. Allows admins to enable floating-point letter grade boundaries.
   1. Allows admins to enable system wide letter dropdowns.
   2. LSU Config
      3. enable custom %, go back to 'letters'
      4. edit letter grades, notice that we can put in anything we want
      5. in letter edit settings,check strict letter names
      6. back in letters, edit, and ensure that only the letters of the scale are allowed
      7. now in a course, in gb settings, select letter > 'real'
      8. ensure that the letters appear correctly in the grader report
1. column_avg_no_zero.patch
   1. Allows faculty to omit explicitly marked 0 grades form column averages as well as empty grades for better column averages.
   2. LSU Config
      3. enable system-wide
      4. notice additional option in 'Grades Selected for column averages'
      5. choose non-empty grades
         6. notice that non-empty grades don't affect the avgs
         7. update course-level setting to 'non-empty, non-zero'
            8. ensure that 0 grades are ignored
         9. update system-wide setting as above, ensure 0 grades are ignored

1. coursecat_editable.patch
   1. Allows admin to disable the ability for users to rename their course category.
   2. LSU
      3. enable and notice that course cat is not editable and takes name of course
1. curve-to.patch
   1. Changes multiplicator into a more user friendly curve-to option.
      1. Example: max points for an item is 75, instructor can curve-to 100, enabling a 1.33333 multiplicator behind the scenes.
      2. LSU Config
         3. enable curve-to
         4. ensure that 'multiplicator is replaced with curve to
         5. ensure that curve to respects 'unlimited' setting for the course in question
1. disable_calculations.patch
   1. Allows the administrator to disable grade calculations site wide, including within all other settings areas.
   2. LSU Config
      3. 2 settings:
         4. default: 'show calc' no
         5. default: 'disable calc' yes
      6. in the default config, notice that calculations are available in the full view
      7. when disabledcalc is true:
         8. notice that calc does not appear in the full view
         9. ensure that 'show calc' setting is not available
1. droplow_limit.patch
   1. Allows admin to require that drop lowest N grades only drop grades after N+1 number of grades are reached.
   2. LSU
      3. keep highest forced, advanced, 
      4. keep lowest not forced,advanced,
      5. drop lowerest limit checked should prevent a user with only 2 grades fromhaving no grade when the teacher drops lowest 2
1. even_odd_rows.patch
   1. Fixes bug where all rows were even in right_scroller in grader report.
1. exclude_and_override.patch
   1. Very simple modification showing the word overridden and excluded within the grader report for overridden and excluded items.
   2. LSU
      3. add a quiz, or anything overrideable
      4. notice that overridden or excluded is called out visually
1. grade_history_cleanup.patch
   1. Allows the administrator to schedule grade history pruning to low usage times for performance reasons.
   2. LSU
      3. cron task
1. hide_minimum.patch
   1. Allows the administrator to hide the minimum grade feature in Moodle for non-scale items.
   2. LSU
      3. grade item settings - 'hide minimum grade'
      4. check for lsu theme disaply:none
      5. notice that min grade is not frozen w/o 'hidemin' checked
      6. with 'hide min' set,notice that the minimum cannot be edited
      7. re-enable the theme/lsu/grade.css and notice that min grade is not displayed
1. keephigh_OR_droplow.patch
   1. Disallows the user from using keep high or drop low if the other has been used for a category.
   2. LSU
      3. keep highest: none, not-forced,advanced
      4. notice that if keep highest is set,drop lowest is unavailable.
1. manual_rawgrade.patch
   1. Allows the administrator to configure manual items to behave like all other graded items in Moodle.
      1. Users can use offseet and multiplicator with manual items with this patch.
      2. LSU un-check 'man item recompute'
         3. notice that curve-to, offset are not availa in the grader report
         4. with this checked,man items use raw grade,hence manipulable via curve-to,etc
1. override_cat.patch
   1. Allows admin to disable the ability for users to override course category totals.
   2. LSU
      2. Turn editing on, ensure course categories are not editable
      3. in grades settings,enable edit cat totals
         4. ensure that cat totals are editable
      5. disable cat totals
         6. ensure you can't edit cat totatl in the g report
         7. ensure that cat totals are not editable in the QE
1. quick_edit_integration.patch
   1. Integrates quick edit links in editable item row headers and in student rows.
   2. LSU
      3. grader report - settings: 'integrate quick edit'
      4. notice that grader report has link for QE on each itemand in the user column
1. repeat_headers.patch
   1. Allows for admin default and user configurable repeating of grader report headers every N rows.
   2. LSU
      3. set the repeat headers setting to somenumber
      4. verify that headers repeat system-wide
      5. set user-preferences and ensure that local setting overrides global
      6. ensure that 0 disables repeat
1. show_weights.patch
   1. Allow admin or end user to show actual weights of items within the grader report.
   2. LSU
      3. check 'show weighted percents' - show s weight of an item in relation to its parent
         4. verify weights show; make changes and verify they areapprop; ec items have no weight
1. student_privacy.patch
   1. Enables admins to require that teachers agree to protect student rights when downloading grades.
   2. LSU
      3. uncheck 'student privacy' 
         4. export grades and notice that there is no warning
      5. re-check 'stu priv'
         6. notice the 'accept' checkbox and that form submissionfails without it
1. swm_ec_weight.patch
   1. Enables the administrator to enable or disable weighted extra credit when the simple weighted mean aggregation method is used.
   2. LSU
      3. 
1. ungraded_manual.patch
   1. Fixes the bug where users have the option to create manual items with NO GRADE grading type.
1. wm_extra_credit.patch
   1. Allows for extra credit in the weighted mean aggregation method.


## LSU Configuration

### Test Setup
* 1 course
 * 1 teacher
 * 2 students
 * 1 group
* build graedbook with gb_builder 
  * add categories with weights homework (10%), paper(40%), exam(30%) and quiz(20%)
