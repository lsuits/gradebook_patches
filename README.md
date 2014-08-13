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
1. better_letters.patch
 1. Fixes hard-coded 2 decimal rounding bug.
 1. Allows admins to enable floating-point letter grade boundaries.
 1. Allows admins to enable system wide letter dropdowns.
1. column_avg_no_zero.patch
 1. Allows faculty to omit explicitly marked 0 grades form column averages as well as empty grades for better column averages.
1. coursecat_editable.patch
 1. Allows admin to disable the ability for users to rename their course category.
1. curve-to.patch
 1. Changes multiplicator into a more user friendly curve-to option.
   1. Example: max points for an item is 75, instructor can curve-to 100, enabling a 1.33333 multiplicator behind the scenes.
1. disable_calculations.patch
 1. Allows the administrator to disable grade calculations site wide, including within all other settings areas.
1. droplow_limit.patch
 1. Allows admin to require that drop lowest N grades only drop grades after N+1 number of grades are reached.
1. even_odd_rows.patch
 1. Fixes bug where all rows were even in right_scroller in grader report.
1. exclude_and_override.patch
 1. Very simple modification showing the word overridden and excluded within the grader report for overridden and excluded items.
1. grade_history_cleanup.patch
 1. Allows the administrator to schedule grade history pruning to low usage times for performance reasons.
1. hide_minimum.patch
 1. Allows the administrator to hide the minimum grade feature in Moodle for non-scale items.
1. keephigh_OR_droplow.patch
 1. Disallows the user from using keep high or drop low if the other has been used for a category.
1. manual_rawgrade.patch
 1. Allows the administrator to configure manual items to behave like all other graded items in Moodle.
  1. Users can use offseet and multiplicator with manual items with this patch.
1. override_cat.patch
 1. Allows admin to disable the ability for users to override course category totals.
1. quick_edit_integration.patch
 1. Integrates quick edit links in editable item row headers and in student rows.
1. repeat_headers.patch
 1. Allows for admin default and user configurable repeating of grader report headers every N rows.
1. show_weights.patch
 1. Allow admin or end user to show actual weights of items within the grader report.
1. student_privacy.patch
 1. Enables admins to require that teachers agree to protect student rights when downloading grades.
1. swm_ec_weight.patch
 1. Enables the administrator to enable or disable weighted extra credit when the simple weighted mean aggregation method is used.
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