^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Changelog for package moveit_core
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

2.1.3 (2021-05-22)
------------------
* Delete exclusive arg for collision detector creation (`#466 <https://github.com/ros-planning/moveit2/issues/466>`_)
  * Delete exclusive arg for collision detector creation
  * Rename setActiveCollisionDetector->allocateCollisionDetector everywhere
* Cleanup collision_distance_field test dependencies (`#465 <https://github.com/ros-planning/moveit2/issues/465>`_)
* Fix PlanningScene CollisionDetector diff handling (`#464 <https://github.com/ros-planning/moveit2/issues/464>`_)
* Fix joint limit handling when velocities aren't included in robot state (`#451 <https://github.com/ros-planning/moveit2/issues/451>`_)
* Contributors: AndyZe, Henning Kayser

2.1.2 (2021-04-20)
------------------
* Fix robot_model & moveit_ros_visualization dependencies (`#421 <https://github.com/ros-planning/moveit2/issues/421>`_)
* Unify PickNik name in copyrights (`#419 <https://github.com/ros-planning/moveit2/issues/419>`_)
* Contributors: Jafar Abdi, Tyler Weaver

2.1.1 (2021-04-12)
------------------
* Update doxygen comments for distance() and interpolate() (`#401 <https://github.com/ros-planning/moveit2/issues/401>`_)
* Add differential drive joint model (`#390 <https://github.com/ros-planning/moveit2/issues/390>`_)
  * RobotModelBuilder: Add new function addJointProperty to add a property for a joint
  * Add angular_distance_weight joint property
  * Add motion_model joint property
  * Add min_translational_distance joint property
* Add initialize function for moveit_sensor_manager plugin (`#386 <https://github.com/ros-planning/moveit2/issues/386>`_)
* Eliminate ability to keep multiple collision detectors updated (`#364 <https://github.com/ros-planning/moveit2/issues/364>`_)
  * Fix seg faults in setCollisionDetectorType()
  * Add unit test for switching collision detector types
* Port of Bullet collision to ROS2 (`#322 <https://github.com/ros-planning/moveit2/issues/322>`_)
* Fix EXPORT install in CMake (`#372 <https://github.com/ros-planning/moveit2/issues/372>`_)
* Bug fixes in main branch (`#362 <https://github.com/ros-planning/moveit2/issues/362>`_)
  * robot_trajectory: Fix bugs in getRobotTrajectoryMsg function
  * controller_manager: Use Duration(-1) as infinite timeout
  * ActionBasedControllerHandle: fix dangling reference in case of timeout
  * TfPublisher: tf frame name can't start with '/'
* Sync main branch with MoveIt 1 from previous head https://github.com/ros-planning/moveit/commit/0247ed0027ca9d7f1a7f066e62c80c9ce5dbbb5e up to https://github.com/ros-planning/moveit/commit/74b3e30db2e8683ac17b339cc124675ae52a5114
* [fix] export cmake library install (`#339 <https://github.com/ros-planning/moveit2/issues/339>`_)
* Clean up collision-related log statements (`#2480 <https://github.com/ros-planning/moveit2/issues/2480>`_)
* Fix RobotState::dropAccelerations/dropEffort to not drop velocities (`#2478 <https://github.com/ros-planning/moveit2/issues/2478>`_)
* Provide a function to set the position of active joints in a JointModelGroup (`#2456 <https://github.com/ros-planning/moveit2/issues/2456>`_)
  * RobotState::setJointGroupPositions: assert correct size of  vector
  * setJointGroupActivePositions sets only the positions of active joints
  * implement JointModelGroup::getActiveVariableCount
* Fix doxygen documentation for setToIKSolverFrame (`#2461 <https://github.com/ros-planning/moveit2/issues/2461>`_)
  * Fix doxygen documentation for setToIKSolverFrame
  * "Convert" -> "Transform"
  * Make function private. Update comments.
  * Make inline and private
  * Longer function should not be inline
* Fix validation of orientation constraints (`#2434 <https://github.com/ros-planning/moveit2/issues/2434>`_)
* RobotModelBuilder: Add parameter to specify the joint rotation axis
* RobotModelBuilder: Allow adding end effectors (`#2454 <https://github.com/ros-planning/moveit2/issues/2454>`_)
* Delete CollisionRequest min_cost_density
* Fix OrientationConstraint::decide (`#2414 <https://github.com/ros-planning/moveit2/issues/2414>`_)
* Changed processing_thread\_ spin to use std::make_unique instead of new (`#2412 <https://github.com/ros-planning/moveit2/issues/2412>`_)
* Update collision-related comments (`#2382 <https://github.com/ros-planning/moveit2/issues/2382>`_) (`#2388 <https://github.com/ros-planning/moveit2/issues/2388>`_)
* Contributors: AndyZe, David V. Lu!!, Henning Kayser, Jafar Abdi, Jorge Nicho, Robert Haschke, Simon Schmeisser, Stuart Anderson, Thomas G, Tyler Weaver, sevangelatos

2.1.0 (2020-11-23)
------------------
* [fix] Clang-tidy fixes (`#264 <https://github.com/ros-planning/moveit2/issues/264>`_, `#210 <https://github.com/ros-planning/moveit2/issues/210>`_)
  * Suppress false-positive clang-tidy fix in DistanceResultsData
  * Fix Eigen alignment in DistanceResultsData
  * Fix readability-identifier-naming, performance-for-range-copy, readability-named-parameter
* [fix] Fixup moveit_resources usage in moveit_core test (`#259 <https://github.com/ros-planning/moveit2/issues/259>`_)
* [maint] Remove deprecated namespaces robot_model, robot_state  (`#276 <https://github.com/ros-planning/moveit2/issues/276>`_)
* [maint] Wrap common cmake code in 'moveit_package()' macro (`#285 <https://github.com/ros-planning/moveit2/issues/285>`_)
  * New moveit_package() macro for compile flags, Windows support etc
  * Add package 'moveit_common' as build dependency for moveit_package()
  * Added -Wno-overloaded-virtual compiler flag for moveit_ros_planners_ompl
* [maint] Compilation fixes for macOS (`#271 <https://github.com/ros-planning/moveit2/issues/271>`_)
* [maint] kinematics_base: remove deprecated initialize function (`#232 <https://github.com/ros-planning/moveit2/issues/232>`_)
* [maint] Update to new moveit_resources layout (`#247 <https://github.com/ros-planning/moveit2/issues/247>`_)
* [maint] Enable "test_time_optimal_trajectory_generation" unit test (`#241 <https://github.com/ros-planning/moveit2/issues/241>`_)
* [maint] CMakeLists dependency cleanup and fixes (`#226 <https://github.com/ros-planning/moveit2/issues/226>`_, `#228 <https://github.com/ros-planning/moveit2/issues/228>`_)
* [ros2-migration] Migrate to ROS 2 Foxy (`#227 <https://github.com/ros-planning/moveit2/issues/227>`_)
* Contributors: Abdullah Alzaidy, Dave Coleman, Henning Kayser, Jafar Abdi, Lior Lustgarten, Mark Moll, Mohmmad Ayman, Robert Haschke, Yu Yan, Tyler Weaver, Sebastian Jahr

2.0.0 (2020-02-17)
------------------
* [improve] Load OMPL planner config parameters
* [fix] Fix double node executor exceptions
  * Load parameters from node instead of SyncParameterClient
* [fix] Load planning request adapter parameters from subnamespace
* [fix] KinematicsBase: fix default value in parameter lookup (`#154 <https://github.com/ros-planning/moveit2/issues/154>`_)
* [sys] Upgrade to ROS 2 Eloquent (`#152 <https://github.com/ros-planning/moveit2/issues/152>`_)
* [sys] Fix CMakeLists.txt files for Eloquent
* [sys] replace rosunit -> ament_cmake_gtest
* [maintenance] Remove redundant build dependency to 'angles'
* [ros2-migration] Build moveit_core with colcon (`#117 <https://github.com/ros-planning/moveit2/issues/117>`_, `#125 <https://github.com/ros-planning/moveit2/issues/125>`_, `#164 <https://github.com/ros-planning/moveit2/issues/164>`_)
* [ros2-migration] Increase CMake version to 3.10.2 per REP 2000 (`#27 <https://github.com/ros-planning/moveit2/issues/27>`_)
* [ros2-migration] Port moveit ros visualization to ROS 2 (`#160 <https://github.com/ros-planning/moveit2/issues/160>`_)
* [ros2-migration] Port moveit_simple_controller_manager to ROS 2 (`#158 <https://github.com/ros-planning/moveit2/issues/158>`_)
* [ros2-migration] Port planning_request_adapter_plugins to ROS 2 (`#62 <https://github.com/ros-planning/moveit2/issues/62>`_, `#87 <https://github.com/ros-planning/moveit2/issues/87>`_, `#114 <https://github.com/ros-planning/moveit2/issues/114>`_)
* [ros2-migration] Port kinematic_constraints to ROS2 (`#42 <https://github.com/ros-planning/moveit2/issues/42>`_)
* [ros2-migration] Port collision_distance_field to ROS 2 (`#65 <https://github.com/ros-planning/moveit2/issues/65>`_)
* [ros2-migration] Port constraint_samplers to ROS 2 (`#60 <https://github.com/ros-planning/moveit2/issues/60>`_)
* [ros2-migration] Port kinematics_base to ROS 2 (`#8 <https://github.com/ros-planning/moveit2/issues/8>`_, `#83 <https://github.com/ros-planning/moveit2/issues/83>`_, `#145 <https://github.com/ros-planning/moveit2/issues/145>`_)
* [ros2-migration] Port collision_detection_fcl to ROS 2 (`#41 <https://github.com/ros-planning/moveit2/issues/41>`_)
* [ros2-migration] Port planning_scene to ROS2 (`#43 <https://github.com/ros-planning/moveit2/issues/43>`_)
* [ros2-migration] Port trajectory_processing to ROS 2 (`#63 <https://github.com/ros-planning/moveit2/issues/63>`_)
* [ros2-migration] Port collision_detection to ROS 2 (`#40 <https://github.com/ros-planning/moveit2/issues/40>`_)
* [ros2-migration] Port distance_field to ROS 2 (`#64 <https://github.com/ros-planning/moveit2/issues/64>`_)
* [ros2-migration] Port background_processing to ROS 2  (`#55 <https://github.com/ros-planning/moveit2/issues/55>`_, `#82 <https://github.com/ros-planning/moveit2/issues/82>`_)
* [ros2-migration] Port controller_manager to ROS 2 (`#84 <https://github.com/ros-planning/moveit2/issues/84>`_)
* [ros2-migration] Port moveit_core_utils to ROS 2 (`#68 <https://github.com/ros-planning/moveit2/issues/68>`_)
* [ros2-migration] Port robot_state to ROS 2 (`#80 <https://github.com/ros-planning/moveit2/issues/80>`_)
* [ros2-migration] Port robot_trajectory to ROS 2 (`#39 <https://github.com/ros-planning/moveit2/issues/39>`_)
* [ros2-migration] Port kinematics_metrics to ROS 2 (`#66 <https://github.com/ros-planning/moveit2/issues/66>`_, `#88 <https://github.com/ros-planning/moveit2/issues/88>`_)
* [ros2-migration] Port planning_interface to ROS 2 (`#61 <https://github.com/ros-planning/moveit2/issues/61>`_, `#86 <https://github.com/ros-planning/moveit2/issues/86>`_)
* [ros2-migration] Port dynamics_solver to ROS 2 (`#67 <https://github.com/ros-planning/moveit2/issues/67>`_, `#89 <https://github.com/ros-planning/moveit2/issues/89>`_)
* [ros2-migration] Port robot_model to ROS 2 (`#10 <https://github.com/ros-planning/moveit2/issues/10>`_)
* [ros2-migration] Port profiler to ROS 2 (`#9 <https://github.com/ros-planning/moveit2/issues/9>`_)
* [ros2-migration] Port transforms to ROS 2 (`#12 <https://github.com/ros-planning/moveit2/issues/12>`_)
* [ros2-migration] Port exceptions to ROS 2 (`#7 <https://github.com/ros-planning/moveit2/issues/7>`_, `#81 <https://github.com/ros-planning/moveit2/issues/81>`_)
* [ros2-migration] Port controller_manager submodule of moveit_core to ROS 2 (`#6 <https://github.com/ros-planning/moveit2/issues/6>`_)
* [ros2-migration] Port version submodule of moveit_core (`#4 <https://github.com/ros-planning/moveit2/issues/4>`_)
* [ros2-migration] Port backtrace to ROS 2 (`#5 <https://github.com/ros-planning/moveit2/issues/5>`_)
* [ros2-migration] Port sensor_manager ROS 2 (`#11 <https://github.com/ros-planning/moveit2/issues/11>`_)
* [ros2-migration] Port macros to ROS 2 (`#3 <https://github.com/ros-planning/moveit2/issues/3>`_)
* Contributors: Abdullah Alzaidy, Alejandro Hernández Cordero, Anas Mchichou El Harrak, Dave Coleman, Henning Kayser, Jafar Abdi, Mark Moll, Michael Görner, Mike Lautman, Mohmmad Ayman, Robert Haschke, Tyler Weaver, Víctor Mayoral Vilches, Yu Yan

1.1.1 (2020-10-13)
------------------
* [feature] Handle multiple link libraries for FCL (`ros-planning:moveit#2325 <https://github.com/ros-planning/moveit/issues/2325>`_)
* [feature] Adapt to API changes in geometric_shapes (`ros-planning:moveit#2324 <https://github.com/ros-planning/moveit/issues/2324>`_)
* [fix] clang-tidy issues (`ros-planning:moveit#2337 <https://github.com/ros-planning/moveit/issues/2337>`_)
* [fix] various issues with Noetic build (`ros-planning:moveit#2327 <https://github.com/ros-planning/moveit/issues/2327>`_)
* [maint] Depend on ros-noetic-fcl (0.6) in Noetic (`ros-planning:moveit#2359 <https://github.com/ros-planning/moveit/issues/2359>`_)
* [maint] Cleanup MSA includes (`ros-planning:moveit#2351 <https://github.com/ros-planning/moveit/issues/2351>`_)
* [maint] Add comment to MOVEIT_CLASS_FORWARD (`ros-planning:moveit#2315 <https://github.com/ros-planning/moveit/issues/2315>`_)
* Contributors: Felix von Drigalski, G.A. vd. Hoorn, Robert Haschke

1.1.0 (2020-09-04)
------------------
* [feature] Add a utility to print collision pairs (`ros-planning:moveit#2275 <https://github.com/ros-planning/moveit/issues/2275>`_)
* [feature] Fix subframes disappearing when object is detached/scaled/renamed (`ros-planning:moveit#1866 <https://github.com/ros-planning/moveit/issues/1866>`_)
* [feature] Use Eigen::Transform::linear() instead of rotation() (`ros-planning:moveit#1964 <https://github.com/ros-planning/moveit/issues/1964>`_)
* [feature] Utilize new geometric_shapes functions to improve performance (`ros-planning:moveit#2038 <https://github.com/ros-planning/moveit/issues/2038>`_)
* [feature] move_group pick place test (`ros-planning:moveit#2031 <https://github.com/ros-planning/moveit/issues/2031>`_)
* [feature] Split collision proximity threshold (`ros-planning:moveit#2008 <https://github.com/ros-planning/moveit/issues/2008>`_)
* [feature] Integration test to defend subframe tutorial (`ros-planning:moveit#1757 <https://github.com/ros-planning/moveit/issues/1757>`_)
* [feature] List missing joints in group states (`ros-planning:moveit#1935 <https://github.com/ros-planning/moveit/issues/1935>`_)
* [feature] Improve documentation for setJointPositions() (`ros-planning:moveit#1921 <https://github.com/ros-planning/moveit/issues/1921>`_)
* [feature] Installs an empty plugin description xml file if bullet is not found (`ros-planning:moveit#1898 <https://github.com/ros-planning/moveit/issues/1898>`_)
* [feature] Bullet collision detection (`ros-planning:moveit#1839 <https://github.com/ros-planning/moveit/issues/1839>`_)
* [feature] Improve RobotState documentation (`ros-planning:moveit#1846 <https://github.com/ros-planning/moveit/issues/1846>`_)
* [feature] Adapt cmake for Bullet (`ros-planning:moveit#1744 <https://github.com/ros-planning/moveit/issues/1744>`_)
* [feature] Unified Collision Environment Bullet (`ros-planning:moveit#1572 <https://github.com/ros-planning/moveit/issues/1572>`_)
* [feature] Adding continuous collision detection to Bullet (`ros-planning:moveit#1551 <https://github.com/ros-planning/moveit/issues/1551>`_)
* [feature] Bullet Collision Detection (`ros-planning:moveit#1504 <https://github.com/ros-planning/moveit/issues/1504>`_)
* [feature] Generic collision detection test suite (`ros-planning:moveit#1543 <https://github.com/ros-planning/moveit/issues/1543>`_)
* [feature] Empty collision checker template for usage with tesseract and bullet (`ros-planning:moveit#1499 <https://github.com/ros-planning/moveit/issues/1499>`_)
* [feature] Add deepcopy option for RobotTrajectory's copy constructor (`ros-planning:moveit#1760 <https://github.com/ros-planning/moveit/issues/1760>`_)
* [feature] Enable code-coverage test (`ros-planning:moveit#1776 <https://github.com/ros-planning/moveit/issues/1776>`_)
* [feature] Provide UniquePtr macros (`ros-planning:moveit#1771 <https://github.com/ros-planning/moveit/issues/1771>`_)
* [feature] Improve variable name in RobotModel (`ros-planning:moveit#1752 <https://github.com/ros-planning/moveit/issues/1752>`_)
* [feature] Adding documentation to collision detection (`ros-planning:moveit#1645 <https://github.com/ros-planning/moveit/issues/1645>`_)
* [feature] Unified Collision Environment Integration (`ros-planning:moveit#1584 <https://github.com/ros-planning/moveit/issues/1584>`_)
* [feature] Document discretization behavior in KinematicsBase (`ros-planning:moveit#1602 <https://github.com/ros-planning/moveit/issues/1602>`_)
* [feature] Rename lm to link_model (`ros-planning:moveit#1592 <https://github.com/ros-planning/moveit/issues/1592>`_)
* [feature] Allow ROS namespaces for planning request adapters (`ros-planning:moveit#1530 <https://github.com/ros-planning/moveit/issues/1530>`_)
* [feature] Add named frames to CollisionObjects (`ros-planning:moveit#1439 <https://github.com/ros-planning/moveit/issues/1439>`_)
* [feature] More verbose "id" argument in PlanningScene, RobotState & CollisionWorld functions (`ros-planning:moveit#1450 <https://github.com/ros-planning/moveit/issues/1450>`_)
* [feature] Separate source file for CartesianInterpolator (`ros-planning:moveit#1149 <https://github.com/ros-planning/moveit/issues/1149>`_)
* [fix] Various fixes for upcoming Noetic release (`ros-planning:moveit#2180 <https://github.com/ros-planning/moveit/issues/2180>`_)
* [fix] Change FloatingJointModel::getStateSpaceDimension return value to 7
* [fix] collision world: check for empty shapes vector before access (`ros-planning:moveit#2026 <https://github.com/ros-planning/moveit/issues/2026>`_)
* [fix] Fix Condition for Adding current DistanceResultData to DistanceMap for DistanceRequestType::SINGLE (`ros-planning:moveit#1963 <https://github.com/ros-planning/moveit/issues/1963>`_)
* [fix] Do not override empty URDF link collision geometry (`ros-planning:moveit#1952 <https://github.com/ros-planning/moveit/issues/1952>`_)
* [fix] Fix issue in unpadded collision checking (`ros-planning:moveit#1899 <https://github.com/ros-planning/moveit/issues/1899>`_)
* [fix] Remove object from collision world only once (`ros-planning:moveit#1900 <https://github.com/ros-planning/moveit/issues/1900>`_)
* [fix] Initialize zero dynamics in CurrentStateMonitor (`ros-planning:moveit#1883 <https://github.com/ros-planning/moveit/issues/1883>`_)
* [fix] getFrameInfo(): Avoid double search for link name (`ros-planning:moveit#1853 <https://github.com/ros-planning/moveit/issues/1853>`_)
* [fix] Fix RobotTrajectory's copy constructor (`ros-planning:moveit#1834 <https://github.com/ros-planning/moveit/issues/1834>`_)
* [fix] Fix flaky moveit_cpp test (`ros-planning:moveit#1781 <https://github.com/ros-planning/moveit/issues/1781>`_)
* [fix] Fix doc string OrientationConstraint (`ros-planning:moveit#1793 <https://github.com/ros-planning/moveit/issues/1793>`_)
* [fix] Move ASSERT() into test setup (`ros-planning:moveit#1657 <https://github.com/ros-planning/moveit/issues/1657>`_)
* [fix] Add missing dependencies to library (`ros-planning:moveit#1746 <https://github.com/ros-planning/moveit/issues/1746>`_)
* [fix] Fix clang-tidy for unified collision environment (`ros-planning:moveit#1638 <https://github.com/ros-planning/moveit/issues/1638>`_)
* [fix] PlanningRequestAdapter::initialize() = 0 (`ros-planning:moveit#1621 <https://github.com/ros-planning/moveit/issues/1621>`_)
* [fix] Fix World::getTransform (`ros-planning:moveit#1553 <https://github.com/ros-planning/moveit/issues/1553>`_)
* [fix] Link moveit_robot_model from moveit_test_utils (`ros-planning:moveit#1534 <https://github.com/ros-planning/moveit/issues/1534>`_)
* [maint] Move constraint representation dox to moveit_tutorials (`ros-planning:moveit#2147 <https://github.com/ros-planning/moveit/issues/2147>`_)
* [maint] Update dependencies for python3 in noetic (`ros-planning:moveit#2131 <https://github.com/ros-planning/moveit/issues/2131>`_)
* [maint] clang-tidy fixes (`ros-planning:moveit#2050 <https://github.com/ros-planning/moveit/issues/2050>`_, `ros-planning:moveit#2004 <https://github.com/ros-planning/moveit/issues/2004>`_, `ros-planning:moveit#1419 <https://github.com/ros-planning/moveit/issues/1419>`_)
* [maint] Replace namespaces robot_state and robot_model with moveit::core (`ros-planning:moveit#1924 <https://github.com/ros-planning/moveit/issues/1924>`_)
* [maint] Rename PR2-related collision test files (`ros-planning:moveit#1856 <https://github.com/ros-planning/moveit/issues/1856>`_)
* [maint] Fix compiler warnings (`ros-planning:moveit#1773 <https://github.com/ros-planning/moveit/issues/1773>`_)
* [maint] Add missing licenses (`ros-planning:moveit#1716 <https://github.com/ros-planning/moveit/issues/1716>`_) (`ros-planning:moveit#1720 <https://github.com/ros-planning/moveit/issues/1720>`_)
* [maint] Move isEmpty() test functions to moveit_core/utils (`ros-planning:moveit#1627 <https://github.com/ros-planning/moveit/issues/1627>`_)
* [maint] Switch from include guards to pragma once (`ros-planning:moveit#1615 <https://github.com/ros-planning/moveit/issues/1615>`_)
* [maint] Remove ! from MoveIt name (`ros-planning:moveit#1590 <https://github.com/ros-planning/moveit/issues/1590>`_)
* Contributors: AndyZe, Aris Synodinos, Ayush Garg, Bryce Willey, Dale Koenig, Dave Coleman, Felix von Drigalski, Henning Kayser, Jafar Abdi, Jens P, Jere Liukkonen, Jeroen, John Stechschulte, Jonas Wittmann, Jonathan Binney, Markus Vieth, Martin Pecka, Michael Ferguson, Michael Görner, Mike Lautman, Niklas Fiedler, Patrick Beeson, Robert Haschke, Sean Yen, Shivang Patel, Tyler Weaver, Wolfgang Merkt, Yu, Yan, tsijs, v4hn

1.0.6 (2020-08-19)
------------------
* [maint] Adapt repository for splitted moveit_resources layout (`ros-planning:moveit#2199 <https://github.com/ros-planning/moveit/issues/2199>`_)
* [maint] Migrate to clang-format-10, Fix warnings
* [maint] Optimize includes (`ros-planning:moveit#2229 <https://github.com/ros-planning/moveit/issues/2229>`_)
* [maint] Fix docs in robot_state.h (`ros-planning:moveit#2215 <https://github.com/ros-planning/moveit/issues/2215>`_)
* Contributors: Jeroen, Markus Vieth, Michael Görner, Robert Haschke

1.0.5 (2020-07-08)
------------------
* [fix]     Fix memory leaks related to geometric shapes usage (`ros-planning:moveit#2138 <https://github.com/ros-planning/moveit/issues/2138>`_)
* [fix]     Prevent collision checking segfault if octomap has NULL root pointer (`ros-planning:moveit#2104 <https://github.com/ros-planning/moveit/issues/2104>`_)
* [feature] Allow to parameterize input trajectory density of Time Optimal trajectory generation (`ros-planning:moveit#2185 <https://github.com/ros-planning/moveit/issues/2185>`_)
* [maint]   Optional C++ version setting (`ros-planning:moveit#2166 <https://github.com/ros-planning/moveit/issues/2166>`_)
* [maint]   Added missing boost::regex dependency (`ros-planning:moveit#2163 <https://github.com/ros-planning/moveit/issues/2163>`_)
* [maint]   PropagationDistanceField: Replace eucDistSq with squaredNorm (`ros-planning:moveit#2101 <https://github.com/ros-planning/moveit/issues/2101>`_)
* [fix]     Fix getTransform() (`ros-planning:moveit#2113 <https://github.com/ros-planning/moveit/issues/2113>`_)
  - PlanningScene::getTransforms().getTransform() -> PlanningScene::getFrameTransform()
  - PlanningScene::getTransforms().canTransform() -> PlanningScene::knowsFrameTransform()
* [fix]     Change FloatingJointModel::getStateSpaceDimension return value to 7 (`ros-planning:moveit#2106 <https://github.com/ros-planning/moveit/issues/2106>`_)
* [fix]     Check for empty quaternion message (`ros-planning:moveit#2089 <https://github.com/ros-planning/moveit/issues/2089>`_)
* [fix]     TOTG: Fix parameterization for single-waypoint trajectories (`ros-planning:moveit#2054 <https://github.com/ros-planning/moveit/issues/2054>`_)
  - RobotState: Added interfaces to zero and remove dynamics
* [maint]   Remove unused angles.h includes (`ros-planning:moveit#1985 <https://github.com/ros-planning/moveit/issues/1985>`_)
* Contributors: Felix von Drigalski, Henning Kayser, Michael Görner, Jere Liukkonen, John Stechschulte, Patrick Beeson, Robert Haschke, Tyler Weaver, Wolfgang Merkt

1.0.4 (2020-05-30)
------------------
* Fix broken IKFast generator (`ros-planning:moveit#2116 <https://github.com/ros-planning/moveit/issues/2116>`_)
* Contributors: Robert Haschke

1.0.3 (2020-04-26)
------------------
* [feature] Allow to filter for joint when creating a RobotTrajectory message (`ros-planning:moveit#1927 <https://github.com/ros-planning/moveit/issues/1927>`_)
* [fix]     Fix RobotState::copyFrom()
* [fix]     Fix segfault in totg (`ros-planning:moveit#1861 <https://github.com/ros-planning/moveit/issues/1861>`_)
* [fix]     Handle incomplete group states
* [fix]     Fix issue in totg giving invalid accelerations (`ros-planning:moveit#1729 <https://github.com/ros-planning/moveit/issues/1729>`_)
* [feature] New isValidVelocityMove() for checking time between two waypoints given velocity (`ros-planning:moveit#684 <https://github.com/ros-planning/moveit/issues/684>`_)
* [maint]   Apply clang-tidy fix to entire code base (`ros-planning:moveit#1394 <https://github.com/ros-planning/moveit/issues/1394>`_)
* [fix]     Fix Condition for adding current DistanceResultData to DistanceMap (`ros-planning:moveit#1968 <https://github.com/ros-planning/moveit/issues/1968>`_)
* [maint]   Fix various build issues on Windows (`ros-planning:moveit#1880 <https://github.com/ros-planning/moveit/issues/1880>`_)
  * remove GCC extensions (`ros-planning:moveit#1583 <https://github.com/ros-planning/moveit/issues/1583>`_)
  * Fix binary artifact install locations. (`ros-planning:moveit#1575 <https://github.com/ros-planning/moveit/issues/1575>`_)
* [maint]   Use CMAKE_CXX_STANDARD to enforce c++14 (`ros-planning:moveit#1607 <https://github.com/ros-planning/moveit/issues/1607>`_)
* [fix]     Delete attached body before adding a new one with same id (`ros-planning:moveit#1821 <https://github.com/ros-planning/moveit/issues/1821>`_)
* [maint]   Provide UniquePtr macros (`ros-planning:moveit#1771 <https://github.com/ros-planning/moveit/issues/1771>`_)
* [maint]   Updated deprecation method: MOVEIT_DEPRECATED -> [[deprecated]] (`ros-planning:moveit#1748 <https://github.com/ros-planning/moveit/issues/1748>`_)
* [feature] Add RobotTrajectory::getDuration() (`ros-planning:moveit#1554 <https://github.com/ros-planning/moveit/issues/1554>`_)
* Contributors: Ayush Garg, Dale Koenig, Dave Coleman, Felix von Drigalski, Jafar Abdi, Jeroen, Michael Görner, Mike Lautman, Niklas Fiedler, Robert Haschke, Sean Yen, Yu, Yan

1.0.2 (2019-06-28)
------------------
* [fix] Removed MessageFilter for /collision_object messages (`ros-planning:moveit#1406 <https://github.com/ros-planning/moveit/issues/1406>`_)
* [fix] Update robot state transforms when initializing a planning scene (`ros-planning:moveit#1474 <https://github.com/ros-planning/moveit/issues/1474>`_)
* [fix] Fix segfault when detaching attached collision object (`ros-planning:moveit#1438 <https://github.com/ros-planning/moveit/issues/1438>`_)
* [fix] Normalize quaternions when adding new or moving collision objects (`ros-planning:moveit#1420 <https://github.com/ros-planning/moveit/issues/1420>`_)
* [fix] Minor bug fixes in (collision) distance field (`ros-planning:moveit#1392 <https://github.com/ros-planning/moveit/issues/1392>`_)
* [fix] Remove obsolete moveit_resources/config.h ()
* [fix] Fix test utilities in moveit_core (`ros-planning:moveit#1391 <https://github.com/ros-planning/moveit/issues/1391>`_, `ros-planning:moveit#1409 <https://github.com/ros-planning/moveit/issues/1409>`_, `ros-planning:moveit#1412 <https://github.com/ros-planning/moveit/issues/1412>`_)
* Contributors: Bryce Willey, Henning Kayser, Mike Lautman, Robert Haschke, tsijs

1.0.1 (2019-03-08)
------------------
* [capability] Graphically print current robot joint states with joint limits (`ros-planning:moveit#1358 <https://github.com/ros-planning/moveit/issues/1358>`_)
* [improve] Apply clang tidy fix to entire code base (Part 1) (`ros-planning:moveit#1366 <https://github.com/ros-planning/moveit/issues/1366>`_)
* Contributors: Dave Coleman, Robert Haschke, Yu, Yan

1.0.0 (2019-02-24)
------------------
* [fix] catkin_lint issues (`ros-planning:moveit#1341 <https://github.com/ros-planning/moveit/issues/1341>`_)
* [fix] invert waypoint velocities on reverse (`ros-planning:moveit#1335 <https://github.com/ros-planning/moveit/issues/1335>`_)
* [fix] Added missing robot state update to iterative spline parameterization to prevent warnings. (`ros-planning:moveit#1298 <https://github.com/ros-planning/moveit/issues/1298>`_)
* [fix] robot_model_test_utils depends on message generation (`ros-planning:moveit#1286 <https://github.com/ros-planning/moveit/issues/1286>`_)
* [improve] cleanup LMA kinematics solver `ros-planning:moveit#1318 <https://github.com/ros-planning/moveit/issues/1318>`_
* [improve] Remove (redundant) random seeding and ros-planning:moveit#attempts from RobotState::setFromIK() as the IK solver perform random seeding themselves. `ros-planning:moveit#1288 <https://github.com/ros-planning/moveit/issues/1288>`_
* [improve] Make FCL shape cache thread-local (`ros-planning:moveit#1316 <https://github.com/ros-planning/moveit/issues/1316>`_)
* [improve] Kinematics tests, kdl cleanup `ros-planning:moveit#1272 <https://github.com/ros-planning/moveit/issues/1272>`_, `ros-planning:moveit#1294 <https://github.com/ros-planning/moveit/issues/1294>`_
* [maintenance] Add coverage analysis for moveit_core (`ros-planning:moveit#1133 <https://github.com/ros-planning/moveit/issues/1133>`_)
* [improve] computeCartesianPath: limit joint-space jumps with IK consistency limits (`ros-planning:moveit#1293 <https://github.com/ros-planning/moveit/issues/1293>`_)
* Contributors: Alexander Gutenkunst, Dave Coleman, Jonathan Binney, Martin Oehler, Michael Görner, Mike Lautman, Robert Haschke, Simon Schmeisser

0.10.8 (2018-12-24)
-------------------
* [enhancement] Tool to generate constraint approximation databases (`ros-planning:moveit#1253 <https://github.com/ros-planning/moveit/issues/1253>`_)
* [fix] Fixed uninitialized RobotState transforms (`ros-planning:moveit#1271 <https://github.com/ros-planning/moveit/issues/1271>`_)
* Contributors: Michael Görner, Robert Haschke

0.10.7 (2018-12-13)
-------------------

0.10.6 (2018-12-09)
-------------------
* [fix] Fixed various memory leaks (`ros-planning:moveit#1104 <https://github.com/ros-planning/moveit/issues/1104>`_)
* [fix] Fixed computation of Jacobian for prismatic joints (`ros-planning:moveit#1192 <https://github.com/ros-planning/moveit/issues/1192>`_)
* [enhancement] Add support for FCL 0.6 (`ros-planning:moveit#1156 <https://github.com/ros-planning/moveit/issues/1156>`_)
* [enhancement] Pass RobotModel to IK, avoiding multiple loading (`ros-planning:moveit#1166 <https://github.com/ros-planning/moveit/issues/1166>`_)
* [enhancement] RobotTrajectory: Allow appending part of other trajectory (`ros-planning:moveit#1213 <https://github.com/ros-planning/moveit/issues/1213>`_)
* [maintenance] Rearranged CHOMP-related modules within moveit_planners/chomp (`ros-planning:moveit#1251 <https://github.com/ros-planning/moveit/issues/1251>`_)
* [maintenance] Replaced Eigen::Affine3d -> Eigen::Isometry3d (`ros-planning:moveit#1096 <https://github.com/ros-planning/moveit/issues/1096>`_)
* [maintenance] Use C++14 (`ros-planning:moveit#1146 <https://github.com/ros-planning/moveit/issues/1146>`_)
* [maintenance] Code Cleanup
  * `ros-planning:moveit#1179 <https://github.com/ros-planning/moveit/issues/1179>`_
  * `ros-planning:moveit#1180 <https://github.com/ros-planning/moveit/issues/1180>`_
  * `ros-planning:moveit#1185 <https://github.com/ros-planning/moveit/issues/1185>`_
  * `ros-planning:moveit#1193 <https://github.com/ros-planning/moveit/issues/1193>`_
  * `ros-planning:moveit#1194 <https://github.com/ros-planning/moveit/issues/1194>`_
  * `ros-planning:moveit#1196 <https://github.com/ros-planning/moveit/issues/1196>`_
* [maintenance] RobotModelBuilder to facilitate testing (`ros-planning:moveit#1176 <https://github.com/ros-planning/moveit/issues/1176>`_)
* Contributors: Robert Haschke, 2scholz, Alex Moriarty, Bryce Willey, Dave Coleman, Immanuel Martini, Michael Görner, Milutin Nikolic

0.10.5 (2018-11-01)
-------------------

0.10.4 (2018-10-29)
-------------------

0.10.3 (2018-10-29)
-------------------
* [fix] compiler warnings (`ros-planning:moveit#1089 <https://github.com/ros-planning/moveit/issues/1089>`_)
* [code] cleanup (`ros-planning:moveit#1107 <https://github.com/ros-planning/moveit/issues/1107>`_, `ros-planning:moveit#1099 <https://github.com/ros-planning/moveit/issues/1099>`_, `ros-planning:moveit#1108 <https://github.com/ros-planning/moveit/issues/1108>`_)
* Contributors: Robert Haschke, Simon Schmeisser

0.10.2 (2018-10-24)
-------------------
* [fix] TFs in subgroups of rigidly-connected links (`ros-planning:moveit#912 <https://github.com/ros-planning/moveit/issues/912>`_)
* [fix] Chomp package handling issue `ros-planning:moveit#1086 <https://github.com/ros-planning/moveit/issues/1086>`_ that was introduced in `ubi-agni/hotfix-ros-planning:moveit#1012 <https://github.com/ubi-agni/hotfix-/issues/1012>`_
* [fix] CurrentStateMonitor update callback for floating joints to handle non-identity joint origins `ros-planning:moveit#984 <https://github.com/ros-planning/moveit/issues/984>`_
* [fix] Eigen alignment issuses due to missing aligned allocation (`ros-planning:moveit#1039 <https://github.com/ros-planning/moveit/issues/1039>`_)
* [fix] illegal pointer access (`ros-planning:moveit#989 <https://github.com/ros-planning/moveit/issues/989>`_)
* [fix] reset moveit_msgs::RobotState.is_diff to false (`ros-planning:moveit#968 <https://github.com/ros-planning/moveit/issues/968>`_) This fixes a regression introduced in `ros-planning:moveit#939 <https://github.com/ros-planning/moveit/issues/939>`_.
* [fix] continous joint limits are always satisfied (`ros-planning:moveit#729 <https://github.com/ros-planning/moveit/issues/729>`_)
* [maintenance] using LOGNAME variable rather than strings (`ros-planning:moveit#1079 <https://github.com/ros-planning/moveit/issues/1079>`_)
* [capability][chomp] Addition of CHOMP planning adapter for optimizing result of other planners (`ros-planning:moveit#1012 <https://github.com/ros-planning/moveit/issues/1012>`_)
* [enhancement] Add missing distance check functions to allValid collision checker (`ros-planning:moveit#986 <https://github.com/ros-planning/moveit/issues/986>`_)
* [enhancement] Allow chains to have only one active joint (`ros-planning:moveit#983 <https://github.com/ros-planning/moveit/issues/983>`_)
* [enhancement] collision_detection convenience (`ros-planning:moveit#957 <https://github.com/ros-planning/moveit/issues/957>`_)
* [doc] Document why to use only one IK attempt in computeCartesianPath (`ros-planning:moveit#1076 <https://github.com/ros-planning/moveit/issues/1076>`_)
* Contributors: Adrian Zwiener, Andrey Troitskiy, Dave Coleman, Jonathan Binney, Michael Görner, Mike Lautman, Mohmmad Ayman, Raghavender Sahdev, Robert Haschke, Simon Schmeisser, dcconner, mike lautman

0.10.1 (2018-05-25)
-------------------
* Clang tidy moveit_core (`ros-planning:moveit#880 <https://github.com/ros-planning/moveit/issues/880>`_) (`ros-planning:moveit#911 <https://github.com/ros-planning/moveit/issues/911>`_)
* Allow to retrieve Jacobian of a child link of a move group. (`ros-planning:moveit#877 <https://github.com/ros-planning/moveit/issues/877>`_)
* migration from tf to tf2 API (`ros-planning:moveit#830 <https://github.com/ros-planning/moveit/issues/830>`_)
* Switch to ROS_LOGGER from CONSOLE_BRIDGE (`ros-planning:moveit#874 <https://github.com/ros-planning/moveit/issues/874>`_)
* Add ability to request detailed distance information from fcl (`ros-planning:moveit#662 <https://github.com/ros-planning/moveit/issues/662>`_)
* allow checking for absolute joint-space jumps in Cartesian path (`ros-planning:moveit#843 <https://github.com/ros-planning/moveit/issues/843>`_)
* Simplify adding colored CollisionObjects (`ros-planning:moveit#810 <https://github.com/ros-planning/moveit/issues/810>`_)
* updateMimicJoint(group->getMimicJointModels()) -> updateMimicJoints(group)
* improve RobotState::updateStateWithLinkAt() (`ros-planning:moveit#765 <https://github.com/ros-planning/moveit/issues/765>`_)
* fix computation of shape_extents\_ of links w/o shapes (`ros-planning:moveit#766 <https://github.com/ros-planning/moveit/issues/766>`_)
* Fix computation of axis-aligned bounding box (`ros-planning:moveit#703 <https://github.com/ros-planning/moveit/issues/703>`_)
* RobotModel::getRigidlyConnectedParentLinkModel()
  ... to compute earliest parent link that is rigidly connected to a given link
* Iterative cubic spline interpolation (`ros-planning:moveit#441 <https://github.com/ros-planning/moveit/issues/441>`_)
* Contributors: Bryce Willey, Ian McMahon, Ken Anderson, Levi Armstrong, Maarten de Vries, Martin Pecka, Michael Görner, Mike Lautman, Patrick Holthaus, Robert Haschke, Victor Lamoine, Xiaojian Ma

0.9.11 (2017-12-25)
-------------------
* [fix] ros-planning:moveit#723; attached bodies are not shown in trajectory visualization anymore `ros-planning:moveit#724 <https://github.com/ros-planning/moveit/issues/724>`_
* [fix] Shortcomings in kinematics plugins `ros-planning:moveit#714 <https://github.com/ros-planning/moveit/issues/714>`_
* Contributors: Henning Kayser, Michael Görner, Robert Haschke

0.9.10 (2017-12-09)
-------------------
* [fix] Add missing logWarn argument (`ros-planning:moveit#707 <https://github.com/ros-planning/moveit/issues/707>`_)
* [fix] IKConstraintSampler: Fixed transform from end-effector to ik chain tip. `ros-planning:moveit#582 <https://github.com/ros-planning/moveit/issues/582>`_
* [fix] robotStateMsgToRobotState: is_diff==true => not empty `ros-planning:moveit#589 <https://github.com/ros-planning/moveit/issues/589>`_
* [capability] Multi DOF Trajectory only providing translation not velocity (`ros-planning:moveit#555 <https://github.com/ros-planning/moveit/issues/555>`_)
* [capability] Adds parameter lookup function for kinematics plugins (`ros-planning:moveit#701 <https://github.com/ros-planning/moveit/issues/701>`_)
* [improve] Make operator bool() explicit `ros-planning:moveit#696 <https://github.com/ros-planning/moveit/pull/696>`_
* [improve] Get msgs from Planning Scene `ros-planning:moveit#663 <https://github.com/ros-planning/moveit/issues/663>`_
* [improve] moveit_core: export DEPENDS on LIBFCL `ros-planning:moveit#632 <https://github.com/ros-planning/moveit/pull/632>`_
* [improve] RobotState: Changed multi-waypoint version of computeCartesianPath to test joint space jumps after all waypoints are generated. (`ros-planning:moveit#576 <https://github.com/ros-planning/moveit/issues/576>`_)
* [improve] Better debug output for IK tip frames (`ros-planning:moveit#603 <https://github.com/ros-planning/moveit/issues/603>`_)
* [improve] New debug console colors YELLOW PURPLE (`ros-planning:moveit#604 <https://github.com/ros-planning/moveit/issues/604>`_)
* Contributors: Dave Coleman, Dennis Hartmann, Henning Kayser, Isaac I.Y. Saito, Jorge Nicho, Michael Görner, Phil, Sarah Elliott, Simon Schmeisser, TroyCordie, v4hn

0.9.9 (2017-08-06)
------------------
* [fix][moveit_core] segfault due to missing string format parameter. (`ros-planning:moveit#547 <https://github.com/ros-planning/moveit/issues/547>`_)
* [fix][moveit_core] doc-comment for robot_state::computeAABB (`ros-planning:moveit#516 <https://github.com/ros-planning/moveit/issues/516>`_)
* Contributors: Martin Pecka, henhenhen

0.9.8 (2017-06-21)
------------------

0.9.7 (2017-06-05)
------------------
* [fix] checks for empty name arrays messages before parsing the robot state message data (`ros-planning:moveit#499 <https://github.com/ros-planning/moveit/issues/499>`_)
* Contributors: Jorge Nicho, Michael Goerner

0.9.6 (2017-04-12)
------------------
* [fix] PlanarJointModel::getVariableRandomPositionsNearBy (`ros-planning:moveit#464 <https://github.com/ros-planning/moveit/issues/464>`_)
* Contributors: Tamaki Nishino

0.9.5 (2017-03-08)
------------------
* [fix][moveit_ros_warehouse] gcc6 build error `ros-planning:moveit#423 <https://github.com/ros-planning/moveit/pull/423>`_
* [enhancement] Remove "catch (...)" instances, catch std::exception instead of std::runtime_error (`ros-planning:moveit#445 <https://github.com/ros-planning/moveit/issues/445>`_)
* Contributors: Bence Magyar, Dave Coleman

0.9.4 (2017-02-06)
------------------
* [fix] PlanningScene: Don't reset color information of existing objects when new entries are added (`ros-planning:moveit#410 <https://github.com/ros-planning/moveit/issues/410>`_)
* [fix] update link transforms in UnionConstraintSampler::project (`ros-planning:moveit#384 <https://github.com/ros-planning/moveit/issues/384>`_)
* [capability Addition of Set Joint Model Group Velocities and Accelerations Functions (`ros-planning:moveit#402 <https://github.com/ros-planning/moveit/issues/402>`_)
* [capability] time parameterization: use constants (`ros-planning:moveit#380 <https://github.com/ros-planning/moveit/issues/380>`_)
* [enhancement] multiple shapes in an attached collision object `ros-planning:moveit#421 <https://github.com/ros-planning/moveit/pull/421>`_
* [maintenance] Use static_cast to cast to const. (`ros-planning:moveit#433 <https://github.com/ros-planning/moveit/issues/433>`_)
* [maintenance] ompl_interface: uniform & simplified handling of the default planner (`ros-planning:moveit#371 <https://github.com/ros-planning/moveit/issues/371>`_)
* Contributors: Dave Coleman, Maarten de Vries, Michael Goerner, Mike Lautman, Ruben

0.9.3 (2016-11-16)
------------------
* [fix] Replace unused service dependency with msg dep (`ros-planning:moveit#361 <https://github.com/ros-planning/moveit/issues/361>`_)
* [fix] cleanup urdfdom compatibility (`ros-planning:moveit#319 <https://github.com/ros-planning/moveit/issues/319>`_)
* [fix] Fix missing compatibility header for Wily `ros-planning:moveit#364 <https://github.com/ros-planning/moveit/issues/364>`_)
* [enhancement] Improved RobotState feedback for setFromIK() (`ros-planning:moveit#342 <https://github.com/ros-planning/moveit/issues/342>`_)
* [maintenance] Updated package.xml maintainers and author emails `ros-planning:moveit#330 <https://github.com/ros-planning/moveit/issues/330>`_
* Contributors: Dave Coleman, Ian McMahon, Robert Haschke

0.9.2 (2016-11-05)
------------------
* [Fix] CHANGELOG encoding for 0.9.1 (Fix `ros-planning:moveit#318 <https://github.com/ros-planning/moveit/issues/318>`_). (`ros-planning:moveit#327 <https://github.com/ros-planning/moveit/issues/327>`_)
* [Capability] compatibility to urdfdom < 0.4 (`ros-planning:moveit#317 <https://github.com/ros-planning/moveit/issues/317>`_)
* [Capability] New isValidVelocityMove() for checking maximum velocity between two robot states given time delta
* [Maintenance] Travis check code formatting (`ros-planning:moveit#309 <https://github.com/ros-planning/moveit/issues/309>`_)
* [Maintenance] Auto format codebase using clang-format (`ros-planning:moveit#284 <https://github.com/ros-planning/moveit/issues/284>`_)
* Contributors: Dave Coleman, Isaac I. Y. Saito, Robert Haschke

0.8.2 (2016-06-17)
------------------
* [feat] planning_scene updates: expose success state to caller. This is required to get the information back for the ApplyPlanningSceneService. `ros-planning:moveit_core#296 <https://github.com/ros-planning/moveit_core/issues/297>`_
* [sys] replaced cmake_modules dependency with eigen
* Contributors: Michael Ferguson, Robert Haschke, Michael Goerner, Isaac I. Y. Saito

0.8.1 (2016-05-19)
------------------
* Corrected check in getStateAtDurationFromStart (cherry-picking `ros-planning:moveit_core#291 <https://github.com/ros-planning/moveit_core/issues/291>`_ from indigo-devel)
* Contributors: Hamal Marino

0.8.0 (2016-05-18)
------------------
* [feat] Added file and trajectory_msg to RobotState conversion functions `ros-planning:moveit_core#267 <https://github.com/ros-planning/moveit_core/issues/267>`_
* [feat] Added setJointVelocity and setJointEffort functions `ros-planning:moveit_core#261 <https://github.com/ros-planning/moveit_core/issues/261>`_
* [feat] KinematicsBase changes `ros-planning:moveit_core#248 <https://github.com/ros-planning/moveit_core/issues/248>`_
* [feat] added an ik_seed_state argument to the new getPositionIK(...) method
* [feat] added new interface method for computing multiple ik solutions for a single pose
* [fix] RevoluteJointModel::computeVariablePositions `ros-planning:moveit_core#282 <https://github.com/ros-planning/moveit_core/issues/282>`_
* [fix] getStateAtDurationFromStart would never execute as the check for number of waypoints was inverted `ros-planning:moveit_core#289 <https://github.com/ros-planning/moveit_core/issues/289>`_
* [fix] Revert "Use libfcl-dev rosdep key in kinetic" `ros-planning:moveit_core#287 <https://github.com/ros-planning/moveit_core/issues/287>`_
* [fix] memory leak in RobotState::attachBody `ros-planning:moveit_core#276 <https://github.com/ros-planning/moveit_core/issues/276>`_. Fixing `ros-planning:moveit_core#275 <https://github.com/ros-planning/moveit_core/issues/275>`_
* [fix] New getOnlyOneEndEffectorTip() function `ros-planning:moveit_core#262 <https://github.com/ros-planning/moveit_core/issues/262>`_
* [fix] issue `ros-planning:moveit_core#258 <https://github.com/ros-planning/moveit_core/issues/258>`_ in jade-devel `ros-planning:moveit_core#266 <https://github.com/ros-planning/moveit_core/issues/266>`_
* [fix] Segfault in parenthesis operator `ros-planning:moveit_core#254 <https://github.com/ros-planning/moveit_core/issues/254>`_
* [fix] API Change of shape_tools `ros-planning:moveit_core#242 <https://github.com/ros-planning/moveit_core/issues/242>`_
* [fix] Fixed bug in KinematicConstraintSet::decide that makes it evaluate only joint_constraints. `ros-planning:moveit_core#250 <https://github.com/ros-planning/moveit_core/issues/250>`_
* [fix] Prevent divide by zero `ros-planning:moveit_core#246 <https://github.com/ros-planning/moveit_core/issues/246>`_
* [fix] removed the 'f' float specifiers and corrected misspelled method name
* [fix] typo MULTIPLE_TIPS_NO_SUPPORTED -> MULTIPLE_TIPS_NOT_SUPPORTED
* [sys] Upgrade to Eigen3 as required in Jade `ros-planning:moveit_core#293 <https://github.com/ros-planning/moveit_core/issues/293>`_
* [sys] [cmake] Tell the compiler about FCL include dirs `ros-planning:moveit_core#263 <https://github.com/ros-planning/moveit_core/issues/263>`_
* [sys] Install static libs `ros-planning:moveit_core#251 <https://github.com/ros-planning/moveit_core/issues/251>`_
* [enhance] Allow a RobotTrajectory to be initialized with a pointer joint model group `ros-planning:moveit_core#245 <https://github.com/ros-planning/moveit_core/issues/245>`_
* [doc] Better documentation and formatting `ros-planning:moveit_core#244 <https://github.com/ros-planning/moveit_core/issues/244>`_
* Contributors: Alexis Ballier, Bastian Gaspers, Christian Dornhege, Dave Coleman, Gary Servin, Ioan A Sucan, Isaac I.Y. Saito, Jim Mainprice, Levi Armstrong, Michael Ferguson, Mihai Pomarlan, Robert Haschke, Sachin Chitta, Sam Pfeiffer, Steven Peters, Severin Lemaignan, jrgnicho, ros-devel, simonschmeisser

0.6.15 (2015-01-20)
-------------------
* add ptr/const ptr types for distance field
* update maintainers
* Contributors: Ioan A Sucan, Michael Ferguson

0.6.14 (2015-01-15)
-------------------
* Add time factor to iterative_time_parametrization
* Contributors: Dave Coleman, Michael Ferguson, kohlbrecher

0.6.13 (2014-12-20)
-------------------
* add getShapePoints() to distance field
* update distance_field API to no longer use geometry_msgs
* Added ability to remove all collision objects directly through API (without using ROS msgs)
* Planning Scene: Ability to offset geometry loaded from stream
* Namespaced pr2_arm_kinematics_plugin tests to allow DEBUG output to be suppressed during testing
* Contributors: Dave Coleman, Ioan A Sucan, Michael Ferguson

0.6.12 (2014-12-03)
-------------------
* Merge pull request `ros-planning:moveit_core#214 <https://github.com/ros-planning/moveit_core/issues/214>`_ from mikeferguson/collision_plugin
  moveit_core components of collision plugins
* Merge pull request `ros-planning:moveit_core#210 <https://github.com/ros-planning/moveit_core/issues/210>`_ from davetcoleman/debug_model
  Fix truncated debug message
* Fixed a number of tests, all are now passing on buildfarm
* Merge pull request `ros-planning:moveit_core#208 <https://github.com/ros-planning/moveit_core/issues/208>`_ from mikeferguson/update_fcl_api
  update to use non-deprecated call
* Contributors: Dave Coleman, Ioan A Sucan, Michael Ferguson

0.6.11 (2014-11-03)
-------------------
* Merge pull request `ros-planning:moveit_core#204 <https://github.com/ros-planning/moveit_core/issues/204>`_ from mikeferguson/indigo-devel
* forward port `ros-planning:moveit_core#198 <https://github.com/ros-planning/moveit_core/issues/198>`_ to indigo
* Contributors: Ioan A Sucan, Michael Ferguson

0.6.10 (2014-10-27)
-------------------
* Made setVerbose virtual in constraint_sampler so that child classes can override
* Manipulability Index Error for few DOF
  When the group has fewer than 6 DOF, the Jacobian is of the form 6xM and when multiplied by its transpose, forms a 6x6 matrix that is singular and its determinant is always 0 (or NAN if the solver cannot calculate it).
  Since calculating the SVD of a Jacobian is a costly operation, I propose to retain the calculation of the Manipulability Index through the determinant for 6 or more DOF (where it produces the correct result), but use the product of the singular values of the Jacobian for fewer DOF.
* Fixed missing test depends for tf_conversions
* Allow setFromIK() with multiple poses to single IK solver
* Improved debug output
* Removed duplicate functionality poseToMsg function
* New setToRandomPositions function with custom rand num generator
* Moved find_package angles to within CATKIN_ENABLE_TESTING
* Getter for all tips (links) of every end effector in a joint model group
* New robot state to (file) stream conversion functions
* Added default values for iostream in print statements
* Change PlanningScene constructor to RobotModelConstPtr
* Documentation and made printTransform() public
* Reduced unnecessary joint position copying
* Added getSubgroups() helper function to joint model groups
* Maintain ordering of poses in order that IK solver expects
* Added new setToRandomPositions function that allows custom random number generator to be specified
* Split setToIKSolverFrame() into two functions
* Add check for correct solver type
* Allowed setFromIK to do whole body IK solving with multiple tips
* Contributors: Acorn, Dave Coleman, Ioan A Sucan, Jonathan Weisz, Konstantinos Chatzilygeroudis, Sachin Chitta, hersh

0.5.10 (2014-06-30)
-------------------
* making Saucy and Trusty version of includes to be compatible with upstream packaging. re: https://github.com/ros/rosdistro/issues/4633
* Contributors: Tully Foote

0.5.9 (2014-06-23)
------------------
* Fixed bug in RevoluteJointModel::distance() giving large negative numbers.
* kinematics_base: added an optional RobotState for context.
* fix pick/place approach/retreat on indigo/14.04
* Fixed bug in RevoluteJointModel::distance() giving large negative numbers.
* IterativeParabolicTimeParameterization now ignores virtual joints.
* kinematics_base: added an optional RobotState for context.
* Removed check for multi-dof joints in iterative_time_parameterization.cpp.
* fix pick/place approach/retreat on indigo/14.04
* IterativeParabolicTimeParameterization now ignores virtual joints.
  When checking if all joints are single-DOF, it accepts multi-DOF joints only if they are
  also virtual.
* Fix compiler warnings
* Address [cppcheck: unreadVariable] warning.
* Address [cppcheck: postfixOperator] warning.
* Address [cppcheck: stlSize] warning.
* Address [-Wunused-value] warning.
* Address [-Wunused-variable] warning.
* Address [-Wreturn-type] warning.
* Address [-Wsign-compare] warning.
* Address [-Wreorder] warning.
* Allow joint model group to have use IK solvers with multiple tip frames
* KinematicsBase support for multiple tip frames and IK requests with multiple poses
* dynamics_solver: fix crashbug
  Ignore joint that does not exist (including the virtual joint if it is part of
  the group).
* Changed KinematicsBase::supportsGroup() to use a more standard call signature.
* Merged with hydro-devel
* Removed unnecessary error output
* Removed todo
* Added support for legacy IK calls without solution_callback
* Merge branch 'hydro-devel' into kinematic_base
* Changed KinematicsBase::supportsGroup() to use a more standard call signature.
* Added empty check.
* computeCartesianPath waypoints double-up fix
  computeCartesianPath appends full trajectories between waypoints when given a vector of waypoints. As trajectories include their endpoints, this leads to the combined trajectory being generated with duplicate points at waypoints, which can lead to pauses or stuttering.
  This change skips the first point in trajectories generated between waypoints.
* avoid unnecessary calculations
* Created supportsGroup() test for IK solvers
* from ros-planning/more-travis-tests
  More Travis test fixes.
* Commented out failing test.
  run_tests_moveit_ros_perception requires glut library, and thus a video card or X server, but I haven't had any luck making such things work on Travis.
* avoid unnecessary calculations
  If we are not going to use the missing vector then we should not create it
  (avoid an expensive operation).
* Code cleanup
* Allow joint model group to have use IK solvers with multiple tip frames
* Authorship
* Fixed missing removeSlash to setValues()
* Feedback and cleaned up comment lengths
* Cleaned up commit
* KinematicsBase support for multiple tip frames and IK requests with multiple poses
* More Travis test fixes.
  Switched test_constraint_samplers.cpp from build-time to run-time reference to moveit_resources.
  Added passing run_tests_moveit_core_gtest_test_robot_state_complex test to .travis.yml.
  Added 'make tests' to .travis.yml to make all tests, even failing ones.
* Contributors: Acorn Pooley, Adolfo Rodriguez Tsouroukdissian, Dave Coleman, Dave Hershberger, Martin Szarski, Michael Ferguson, Sachin Chitta, hersh, sachinc

0.5.8 (2014-03-03)
------------------
* Dix bad includes after upstream catkin fix
* update how we find eigen: this is needed for indigo
* Contributors: Ioan A Sucan, Dirk Thomas, Vincent Rabaud

0.5.7 (2014-02-27)
------------------
* Constraint samplers bug fix and improvements
* fix for reverting PR ros-planning:moveit_core#148
* Fix joint variable location segfault
* Better enforce is_valid as a flag that indicated proper configuration has been completed, added comments and warning
* Fix fcl dependency in CMakeLists.txt
* Fixed asymmetry between planning scene read and write.
* Improved error output for state conversion
* Added doxygen for RobotState::attachBody() warning of danger.
* Improved error output for state converstion
* Debug and documentation
* Added new virtual getName() function to constraint samplers
* Made getName() const with static variable
* KinematicsMetrics crashes when called with non-chain groups.
* Added prefixes to debug messages
* Documentation / comments
* Fixed asymmetry between planning scene read and write.
* Added new virtual getName function to constraint samplers for easier debugging and plugin management
* KinematicsMetrics no longer crashes when called with non-chain groups.
* Added doxygen for RobotState::attachBody() warning of danger.
* resolve full path of fcl library
  Because it seems to be common practice to ignore ${catkin_LIBRARY_DIRS}
  it's more easy to resolve the full library path here instead.
* Fix fcl dependency in CMakeLists.txt
  See http://answers.ros.org/question/80936 for details
  Interestingly collision_detection_fcl already uses the correct
  variable ${LIBFCL_LIBRARIES} although it wasn't even set before
* Contributors: Dave Coleman, Dave Hershberger, Ioan A Sucan, Sachin Chitta, sachinc, v4hn

0.5.6 (2014-02-06)
------------------
* fix mix-up comments, use getCollisionRobotUnpadded() since this function is checkCollisionUnpadded.
* Updated tests to new run-time usage of moveit_resources.
* robot_state: comment meaning of default
* Trying again to fix broken tests.
* document RobotState methods
* transforms: clarify comment
* Fixed build of test which depends on moveit_resources.
* Removed debug-write in CMakeLists.txt.
* Added running of currently passing tests to .travis.yml.
* Add kinematic options when planning for CartesianPath
* -Fix kinematic options not getting forwarded, which can lead to undesired behavior in some cases
* Added clarifying doxygen to collision_detection::World::Object.

0.5.5 (2013-12-03)
------------------
* Fix for computing jacobian when the root_joint is not an active joint.
* RobotState: added doxygen comments clarifying action of attachBody().
* Always check for dirty links.
* Update email addresses.
* Robot_state: fix copy size bug.
* Corrected maintainer email.
* Fixed duration in robottrajectory.swap.
* Fixing distance field bugs.
* Compute associated transforms bug fixed.
* Fixing broken tests for changes in robot_state.
* Fixed doxygen function-grouping.
* Fix `ros-planning:moveit_core#95 <https://github.com/ros-planning/moveit_core/issues/95>`_.
* More docs for RobotState.

0.5.4 (2013-10-11)
------------------
* Add functionality for enforcing velocity limits; update API to better naming to cleanly support the new additions
* Adding Travis Continuous Integration to MoveIt
* remember if a group could be a parent of an eef, even if it is not the default one

0.5.3 (2013-09-25)
------------------
* remove use of flat_map

0.5.2 (2013-09-23)
------------------
* Rewrite RobotState and significantly update RobotModel; lots of optimizations
* add support for diffs in RobotState
* fix `ros-planning:moveit_core#87 <https://github.com/ros-planning/moveit_core/issues/87>`_
* add non-const variants for getRobotMarkers
* use trajectory_msgs::JointTrajectory for object attach information instead of sensor_msgs::JointState
* add effort to robot state
* do not include mimic joints or fixed joints in the set of joints in a robot trajectory
* voxel_grid: finish adding Eigen accessors
* voxel_grid: add Eigen accessors
* eliminate determineCollisionPoints() and distance_field_common.h
* propagation_distance_field: make getNearestCell() work with max_dist cells
* distance_field: fix bug in adding shapes
* propagation_distance_field: add getNearestCell()

0.5.1 (2013-08-13)
------------------
* remove CollisionMap message, allow no link name in for AttachedCollisionObject REMOVE operations
* make headers and author definitions aligned the same way; white space fixes
* move background_processing lib to core
* enable RTTI for CollisionRequest
* added ability to find attached objects for a group
* add function for getting contact pairs

0.5.0 (2013-07-15)
------------------
* move msgs to common_msgs

0.4.7 (2013-07-12)
------------------
* doc updates
* white space fixes (tabs are now spaces)
* update root joint if needed, after doing backward fk
* adding options struct to kinematics base
* expose a planning context in the planning_interface base library

0.4.6 (2013-07-03)
------------------
* Added ability to change planner configurations in the interface
* add docs for controller manager
* fix computeTransformBackward()

0.4.5 (2013-06-26)
------------------
* add computeBackwardTransform()
* bugfixes for voxel_grid, distance_field
* slight improvements to profiler
* Fixes compile failures on OS X with clang
* minor speedup in construction of RobotState
* fix time parametrization crash due to joints that have ros-planning:moveit_core#variables!=1
* remove re-parenting of URDF models feature (we can do it cleaner in a different way)

0.4.4 (2013-06-03)
------------------
* fixes for hydro
* be careful about when to add a / in front of the frame name

0.4.3 (2013-05-31)
------------------
* remove distinction of loaded and active controllers

0.4.2 (2013-05-29)
------------------
* generate header with version information

0.4.1 (2013-05-27)
------------------
* fix `ros-planning:moveit_core#66 <https://github.com/ros-planning/moveit_core/issues/66>`_
* rename getTransforms() to copyTransforms()
* refactor how we deal with frames; add a separate library
* remove direction from CollisionResult

0.4.0 (2013-05-23)
------------------
* attempt to fix `ros-planning:moveit_core#241 <https://github.com/ros-planning/moveit_core/issues/241>`_ from moveit_ros
* update paths so that files are found in the globally installed moveit_resources package
* remove magical 0.2 and use of velocity_map
* Work on issue `ros-planning:moveit_core#35 <https://github.com/ros-planning/moveit_core/issues/35>`_.

0.3.19 (2013-05-02)
-------------------
* rename getAttachPosture to getDetachPosture
* add support for attachment postures and implement MOVE operation for CollisionObject
* add ability to fill in planning scene messages by component
* when projection from start state fails for IK samplers, try random states
* bugfixes

0.3.18 (2013-04-17)
-------------------
* allow non-const access to kinematic solver
* bugfix: always update variable transform

0.3.17 (2013-04-16)
-------------------
* bugfixes
* add console colors
* add class fwd macro
* cleanup API of trajectory lookup
* Added method to get joint type as string
* fixing the way mimic joints are updated
* fixed tests

0.3.16 (2013-03-15)
-------------------
* bugfixes
* robot_state::getFrameTransform now returns a ref instead of a pointer; fixed a bug in transforming Vector3 with robot_state::Transforms, add planning_scene::getFrameTransform
* add profiler tool (from ompl)

0.3.15 (2013-03-08)
-------------------
* Remove configure from PlanningScene
* return shared_ptr from getObject() (was ref to shared_ptr)
* use NonConst suffix on PlanningScene non-const get functions.
* make setActiveCollisionDetector(string) return bool status
* use CollisionDetectorAllocator in PlanningScene
* add World class
* bodies attached to the same link should not collide
* include velocities in conversions
* Added more general computeCartesianPath, takes vector of waypoints
* efficiency improvements

0.3.14 (2013-02-05)
-------------------
* initialize controller state by default
* fix `ros-planning:moveit_core#157 <https://github.com/ros-planning/moveit_core/issues/157>`_ in moveit_ros
* fix moveit_ros/`ros-planning:moveit_core#152 <https://github.com/ros-planning/moveit_core/issues/152>`_

0.3.13 (2013-02-04 23:25)
-------------------------
* add a means to get the names of the known states (as saved in SRDF)
* removed kinematics planner

0.3.12 (2013-02-04 13:16)
-------------------------
* Adding comments to voxel grid
* Adding in octree constructor and some additional fields and tests
* Getting rid of obstacle_voxel set as it just slows things down
* Removing pf_distance stuff, adding some more performance, getting rid of addCollisionMapToField function
* Fixing some bugs for signed distance field and improving tests
* Merging signed functionality into PropagateDistanceField, adding remove capabilities, and adding a few comments and extra tests

0.3.11 (2013-02-02)
-------------------
* rename KinematicState to RobotState, KinematicTrajectory to RobotTrajectory
* remove warnings about deprecated functions, use a deque instead of vector to represent kinematic trajectories

0.3.10 (2013-01-28)
-------------------
* fix `ros-planning:moveit_core#28 <https://github.com/ros-planning/moveit_core/issues/28>`_
* improves implementation of metaball normal refinement for octomap
* add heuristic to detect jumps in joint-space distance
* make it such that when an end effector is looked up by group name OR end effector name, things work as expected
* removed urdf and srdf from configure function since kinematic model is also passed in
* make sure decoupling of scenes from parents that are themselves diffs to other scenes actually works
* Fix KinematicState::printStateInfo to actually print to the ostream given.
* add option to specify whether the reference frame should be global or not when computing Cartesian paths
* update API for trajectory smoother
* add interpolation function that takes joint velocities into account, generalize setDiffFromIK
* add option to reverse trajectories
* add computeCartesianPath()
* add ability to load & save scene geometry as text
* compute jacobian with kdl
* fix `ros-planning:moveit_core#15 <https://github.com/ros-planning/moveit_core/issues/15>`_

0.3.9 (2013-01-05)
------------------
* adding logError when kinematics solver not instantiated, also changing @class
* move some functions to a anonymous namespace
* add doc for kinematic_state ns

0.3.8 (2013-01-03)
------------------
* add one more CATKIN dep

0.3.7 (2012-12-31)
------------------
* add capabilities related to reasoning about end-effectors

0.3.6 (2012-12-20)
------------------
* add ability to specify external sampling constraints for constraint samplers

0.3.5 (2012-12-19 01:40)
------------------------
* fix build system

0.3.4 (2012-12-19 01:32)
------------------------
* add notion of default number of IK attempts
* added ability to use IK constraints in sampling with IK samplers
* fixing service request to take proper group name, check for collisions
* make setFromIK() more robust

0.3.3 (2012-12-09)
------------------
* adding capability for constraint aware kinematics + consistency limits to joint state group
* changing the way consistency limits are specified
* speed up implementation of infinityNormDistance()
* adding distance functions and more functions to sample near by
* remove the notion of PlannerCapabilities

0.3.2 (2012-12-04)
------------------
* robustness checks + re-enabe support for octomaps
* adding a bunch of functions to sample near by

0.3.1 (2012-12-03)
------------------
* update debug messages for dealing with attached bodies, rely on the conversion functions more
* changing manipulability calculations
* adding docs
* log error if joint model group not found
* cleaning up code, adding direct access api for better efficiency

0.3.0 (2012-11-30)
------------------
* added a helper function

0.2.12 (2012-11-29)
-------------------
* fixing payload computations
* Changing pr2_arm_kinematics test plugin for new kinematics_base changes
* Finished updating docs, adding tests, and making some small changes to the function of UnionConstraintSampler and ConstraintSamplerManager
* Some extra logic for making sure that a set of joint constraints has coverage for all joints, and some extra tests and docs for constraint sampler manager
* adding ik constraint sampler tests back in, and modifying dependencies such that everything builds
* Changing the behavior of default_constraint_sampler JointConstraintSampler to support detecting conflicting constraints or one constraint that narrows another value, and adding a new struct for holding data.  Also making kinematic_constraint ok with values that are within 2*epsilon of the limits

0.2.11 (2012-11-28)
-------------------
* update kinematics::KinematicBase API and add the option to pass constraints to setFromIK() in KinematicState

0.2.10 (2012-11-25)
-------------------
* minor reorganization of code
* fix `ros-planning:moveit_core#10 <https://github.com/ros-planning/moveit_core/issues/10>`_

0.2.9 (2012-11-23)
------------------
* minor bugfix

0.2.8 (2012-11-21)
------------------
* removing deprecated functions

0.2.7 (2012-11-19)
------------------
* moving sensor_manager and controller_manager from moveit_ros

0.2.6 (2012-11-16 14:19)
------------------------
* reorder includes
* add group name option to collision checking via planning scene functions

0.2.5 (2012-11-14)
------------------
* update DEPENDS
* robustness checks

0.2.4 (2012-11-12)
------------------
* add setVariableBounds()
* read information about passive joints from srdf

0.2.3 (2012-11-08)
------------------
* using srdf info for `ros-planning:moveit_core#6 <https://github.com/ros-planning/moveit_core/issues/6>`_
* fix `ros-planning:moveit_core#6 <https://github.com/ros-planning/moveit_core/issues/6>`_

0.2.2 (2012-11-07)
------------------
* add processPlanningSceneWorldMsg()
* Adding and fixing tests
* Adding docs
* moves refineNormals to new file in collision_detection
* Fixed bugs in PositionConstraint, documented Position and Orientation constraint, extended tests for Position and OrientationConstraint and started working on tests for VisibilityConstraint
* more robust checking of joint names in joint constraints
* adds smoothing to octomap normals; needs better testing

0.2.1 (2012-11-06)
------------------
* revert some of the install location changes

0.2.0 (2012-11-05)
------------------
* update install target locations

0.1.19 (2012-11-02)
-------------------
* add dep on kdl_parser

0.1.18 (2012-11-01)
-------------------
* add kinematics_metrics & dynamics_solver to build process

0.1.17 (2012-10-27 18:48)
-------------------------
* fix DEPENDS libs

0.1.16 (2012-10-27 16:14)
-------------------------
* more robust checking of joint names in joint constraints
* KinematicModel and KinematicState are independent; need to deal with transforms and conversions next

0.1.15 (2012-10-22)
-------------------
* moving all headers under include/moveit/ and using console_bridge instead of rosconsole

0.1.14 (2012-10-20 11:20)
-------------------------
* fix typo

0.1.13 (2012-10-20 10:51)
-------------------------
* removing no longer needed deps
* add ``moveit_`` prefix for all generated libs

0.1.12 (2012-10-18)
-------------------
* porting to new build system
* moved some libraries to moveit_planners
* add access to URDF and SRDF in planning_models
* Adding in path constraints for validating states, needs more testing

0.1.11 (2012-09-20 12:55)
-------------------------
* update conversion functions for kinematic states to support attached bodies

0.1.10 (2012-09-20 10:34)
-------------------------
* making JointConstraints + their samplers work with local variables for multi_dof joints
* Remove fast time parameterization and zero out waypoint times
* setting correct error codes
* bugfixes
* changing the way subgroups are interpreted

0.1.9 (2012-09-14)
------------------
* bugfixes

0.1.8 (2012-09-12 20:56)
------------------------
* bugfixes

0.1.7 (2012-09-12 18:56)
------------------------
* bugfixes

0.1.6 (2012-09-12 18:39)
------------------------
* add install targets, fix some warnings and errors

0.1.5 (2012-09-12 17:25)
------------------------
* first release
