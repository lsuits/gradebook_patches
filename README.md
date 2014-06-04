LSU GradeBook Patches
=================
###All patches are for Moodle 2.7
#How to apply
From your Moodle wwwroot folder:
```
patch -p1 < /path/to/patch.patch
```
#Patches for individual LSU gradebook features.
1. better_letters.patch
 1. Fixes hard-coded 2 decimal rounding bug.
 1. Allows admins to enable floating-point letter grade boundaries.
 1. Allows admins to enable system wide letter dropdowns.
1. coursecat_editable.patch
 1. Allows admin to disable the ability for users to rename their course category.
1. curve-to.patch
 1. Changes multiplicator into a more user friendly curve-to option.
  1. Example: max points for an item is 75, instructor can curve-to 100, enabling a 1.33333 multiplicator behind the scenes.
1. disable_calculations.patch
 1. Allows the administrator to disable grade calculations site wide, including within all other settings areas.
1. droplow_limit.patch
 1. Allows admin to require that drop lowest N grades only drop grades after N+1 number of grades are reached.
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
1. student_privacy.patch
 1. Enables admins to require that teachers agree to protect student rights when downloading grades.
1. ungraded_manual.patch
 1. Fixes the bug where users have the option to create manual items with NO GRADE grading type.
1. wm_extra_credit.patch
 1. Allows for extra credit in the weighted mean aggregation method.
 1. Also allows for a setting to disable weighted extra credit.
