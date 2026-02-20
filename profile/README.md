<div align="center">
  <a href="https://video-reason.com/">
    <img src="https://video-reason.com/static/images/VBVR_logo.png" height="100" alt="VBVR Logo"/>
  </a>

  <h1>VBVR-DataFactory</h1>
  <h3>150 Open-Source Task Generators for Video Reasoning</h3>

  <p>
    <a href="https://video-reason.com/"><img src="https://img.shields.io/badge/Website-video--reason.com-000000?style=for-the-badge" alt="Website"/></a>
    <a href="https://video-reason.com/"><img src="https://img.shields.io/badge/Paper-VBVR-b31b1b?style=for-the-badge" alt="Paper"/></a>
    <a href="https://huggingface.co/VideoReason"><img src="https://img.shields.io/badge/HuggingFace-VideoReason-FFD21E?style=for-the-badge&logo=huggingface&logoColor=000" alt="HuggingFace"/></a>
    <a href="https://join.slack.com/t/vm-dataset/shared_invite/zt-3mdb2lkye-lm7ZC4OGxxRRMEi1M65hKQ"><img src="https://img.shields.io/badge/Community-Slack-4A154B?style=for-the-badge&logo=slack&logoColor=white" alt="Slack"/></a>
  </p>
</div>

---

This organization hosts the **parameterized data generators** that power [VBVR (Very Big Video Reasoning)](https://video-reason.com/) &mdash; a large-scale dataset and benchmark for studying reasoning in video generation models.

Each repository is a self-contained **task generator**: a deterministic program that produces (first frame, prompt, final frame, ground-truth video) tuples for a specific reasoning task. Together, they produce 2M+ images and 1M+ video clips across 200+ tasks.

<table>
<tr>
<td align="center"><h3>150</h3>Open-Source Generators</td>
<td align="center"><h3>5</h3>Cognitive Categories</td>
<td align="center"><h3>3</h3>Dataset Splits</td>
<td align="center"><h3>50+</h3>Contributors</td>
</tr>
</table>

---

## Organization Structure

| Type | Count | Description |
|:--|:--:|:--|
| **Templates** | 2 | Starter repos for building new generators and pipelines |
| **Training Set Generators** | 50 | Tasks used for model training |
| **In-Domain Test Generators** | 50 | Tasks for in-distribution evaluation |
| **Out-of-Domain Test Generators** | 50 | Tasks for out-of-distribution generalization testing |

All generators follow a standard interface:

```
Generator(seed, params)  ->  first_frame.png, prompt.txt, final_frame.png, ground_truth.mp4
```

---

## Templates

Start here if you want to contribute or run generators locally:

| Repository | Description |
|:--|:--|
| [`template-data-generator`](https://github.com/VBVR-DataFactory/template-data-generator) | Starter template for building a new task generator |
| [`template-data-pipeline`](https://github.com/VBVR-DataFactory/template-data-pipeline) | Template for converting external datasets into VBVR format |

---

## Task Catalog

All 150 open-source generators organized by cognitive category. Each task targets one of five foundational faculties grounded in cognitive science:

### Perception &mdash; 45 tasks

Extraction of structured representations from sensory input.

<details>
<summary><b>Training Set</b> (15 tasks)</summary>

| ID | Task | Repository |
|:--|:--|:--|
| G-4 | Identify Objects | [`G-4_identify_objects_data-generator`](https://github.com/VBVR-DataFactory/G-4_identify_objects_data-generator) |
| G-19 | Sort Objects By Rule | [`G-19_sort_objects_by_rule_data-generator`](https://github.com/VBVR-DataFactory/G-19_sort_objects_by_rule_data-generator) |
| G-22 | Attention Shift Same | [`G-22_attention_shift_same_data-generator`](https://github.com/VBVR-DataFactory/G-22_attention_shift_same_data-generator) |
| G-132 | Find Fragment For Gap Filling | [`G-132_find_fragment_for_gap_filling_data-generator`](https://github.com/VBVR-DataFactory/G-132_find_fragment_for_gap_filling_data-generator) |
| G-137 | Identify Figure In Overlapping Area | [`G-137_identify_figure_in_overlapping_area_data-generator`](https://github.com/VBVR-DataFactory/G-137_identify_figure_in_overlapping_area_data-generator) |
| G-141 | Identify Polygon With Most Sides | [`G-141_identify_polygon_with_most_sides_data-generator`](https://github.com/VBVR-DataFactory/G-141_identify_polygon_with_most_sides_data-generator) |
| G-143 | Select Box With Most Dots | [`G-143_select_box_with_most_dots_data-generator`](https://github.com/VBVR-DataFactory/G-143_select_box_with_most_dots_data-generator) |
| G-146 | Circle All Squares From Mixed Shapes | [`G-146_circle_all_squares_from_mixed_shapes_data-generator`](https://github.com/VBVR-DataFactory/G-146_circle_all_squares_from_mixed_shapes_data-generator) |
| G-165 | Mark Tangent Point After Motion | [`G-165_mark_tangent_point_after_motion_data-generator`](https://github.com/VBVR-DataFactory/G-165_mark_tangent_point_after_motion_data-generator) |
| G-166 | Highlight Horizontal Lines | [`G-166_highlight_horizontal_lines_data-generator`](https://github.com/VBVR-DataFactory/G-166_highlight_horizontal_lines_data-generator) |
| G-195 | Select Nearest 2:1 Rectangle | [`G-195_select_nearest_2_1_rectangle_data-generator`](https://github.com/VBVR-DataFactory/G-195_select_nearest_2_1_rectangle_data-generator) |
| G-198 | Mark Right Angled Triangles | [`G-198_mark_right_angled_triangles_data-generator`](https://github.com/VBVR-DataFactory/G-198_mark_right_angled_triangles_data-generator) |
| G-199 | Locate Line Intersections | [`G-199_locate_line_intersections_data-generator`](https://github.com/VBVR-DataFactory/G-199_locate_line_intersections_data-generator) |
| O-1 | Color Mixing | [`O-1_color_mixing_data-generator`](https://github.com/VBVR-DataFactory/O-1_color_mixing_data-generator) |
| O-17 | Color Subtraction | [`O-17_color_subtraction_data-generator`](https://github.com/VBVR-DataFactory/O-17_color_subtraction_data-generator) |

</details>

<details>
<summary><b>In-Domain Test Set</b> (11 tasks)</summary>

| ID | Task | Repository |
|:--|:--|:--|
| G-3 | Stable Sort | [`G-3_stable_sort_data-generator`](https://github.com/VBVR-DataFactory/G-3_stable_sort_data-generator) |
| G-5 | Multi Object Placement | [`G-5_multi_object_placement_data-generator`](https://github.com/VBVR-DataFactory/G-5_multi_object_placement_data-generator) |
| G-9 | Identify Objects In Region | [`G-9_identify_objects_in_region_data-generator`](https://github.com/VBVR-DataFactory/G-9_identify_objects_in_region_data-generator) |
| G-39 | Attention Shift Different | [`G-39_attention_shift_different_data-generator`](https://github.com/VBVR-DataFactory/G-39_attention_shift_different_data-generator) |
| G-43 | Understand Scene Structure | [`G-43_understand_scene_structure_data-generator`](https://github.com/VBVR-DataFactory/G-43_understand_scene_structure_data-generator) |
| G-138 | Spot Unique Non-Repeated Color | [`G-138_spot_unique_non_repeated_color_data-generator`](https://github.com/VBVR-DataFactory/G-138_spot_unique_non_repeated_color_data-generator) |
| G-158 | Identify All Hollow Points | [`G-158_identify_all_hollow_points_data-generator`](https://github.com/VBVR-DataFactory/G-158_identify_all_hollow_points_data-generator) |
| O-16 | Color Addition | [`O-16_color_addition_data-generator`](https://github.com/VBVR-DataFactory/O-16_color_addition_data-generator) |
| O-31 | Ball Eating | [`O-31_ball_eating_data-generator`](https://github.com/VBVR-DataFactory/O-31_ball_eating_data-generator) |
| O-33 | Counting Object | [`O-33_counting_object_data-generator`](https://github.com/VBVR-DataFactory/O-33_counting_object_data-generator) |
| O-38 | Majority Color | [`O-38_majority_color_data-generator`](https://github.com/VBVR-DataFactory/O-38_majority_color_data-generator) |

</details>

<details>
<summary><b>Out-of-Domain Test Set</b> (19 tasks)</summary>

| ID | Task | Repository |
|:--|:--|:--|
| G-54 | Connecting Color | [`G-54_connecting_color_data-generator`](https://github.com/VBVR-DataFactory/G-54_connecting_color_data-generator) |
| G-136 | Locate Point In Overlapping Area | [`G-136_locate_point_in_overlapping_area_data-generator`](https://github.com/VBVR-DataFactory/G-136_locate_point_in_overlapping_area_data-generator) |
| G-147 | Identify Unique Figure In Uniform Set | [`G-147_identify_unique_figure_in_uniform_set_data-generator`](https://github.com/VBVR-DataFactory/G-147_identify_unique_figure_in_uniform_set_data-generator) |
| G-161 | Mark Second Largest Shape | [`G-161_mark_second_largest_shape_data-generator`](https://github.com/VBVR-DataFactory/G-161_mark_second_largest_shape_data-generator) |
| G-167 | Select Longest Polygon Side | [`G-167_select_longest_polygon_side_data-generator`](https://github.com/VBVR-DataFactory/G-167_select_longest_polygon_side_data-generator) |
| G-168 | Identify Nearest To Square Rectangle | [`G-168_identify_nearest_to_square_rectangle_data-generator`](https://github.com/VBVR-DataFactory/G-168_identify_nearest_to_square_rectangle_data-generator) |
| G-169 | Locate Intersection Of Segments | [`G-169_locate_intersection_of_segments_data-generator`](https://github.com/VBVR-DataFactory/G-169_locate_intersection_of_segments_data-generator) |
| G-174 | Arrange Circles By Circumference | [`G-174_arrange_circles_by_circumference_data-generator`](https://github.com/VBVR-DataFactory/G-174_arrange_circles_by_circumference_data-generator) |
| G-189 | Draw Midpoint Perpendicular Line | [`G-189_draw_midpoint_perpendicular_line_data-generator`](https://github.com/VBVR-DataFactory/G-189_draw_midpoint_perpendicular_line_data-generator) |
| G-202 | Mark Wave Peaks | [`G-202_mark_wave_peaks_data-generator`](https://github.com/VBVR-DataFactory/G-202_mark_wave_peaks_data-generator) |
| G-206 | Identify Pentagons | [`G-206_identify_pentagons_data-generator`](https://github.com/VBVR-DataFactory/G-206_identify_pentagons_data-generator) |
| G-212 | Find Incorrect Arrow Direction | [`G-212_find_incorrect_arrow_direction_data-generator`](https://github.com/VBVR-DataFactory/G-212_find_incorrect_arrow_direction_data-generator) |
| G-218 | Identify Largest Angle In Triangle | [`G-218_identify_largest_angle_in_triangle_data-generator`](https://github.com/VBVR-DataFactory/G-218_identify_largest_angle_in_triangle_data-generator) |
| G-222 | Mark Tangent Point Of Circles | [`G-222_mark_tangent_point_of_circles_data-generator`](https://github.com/VBVR-DataFactory/G-222_mark_tangent_point_of_circles_data-generator) |
| G-223 | Highlight Horizontal Lines | [`G-223_highlight_horizontal_lines_data-generator`](https://github.com/VBVR-DataFactory/G-223_highlight_horizontal_lines_data-generator) |
| G-248 | Mark Asymmetrical Shape | [`G-248_mark_asymmetrical_shape_data-generator`](https://github.com/VBVR-DataFactory/G-248_mark_asymmetrical_shape_data-generator) |
| G-250 | Color Triple Intersection Red | [`G-250_color_triple_intersection_red_data-generator`](https://github.com/VBVR-DataFactory/G-250_color_triple_intersection_red_data-generator) |
| O-2 | Pigment Color Mixing (Subtractive) | [`O-2_pigment_color_mixing_subtractive_data-generator`](https://github.com/VBVR-DataFactory/O-2_pigment_color_mixing_subtractive_data-generator) |
| O-65 | Animal Size Sorting | [`O-65_animal_size_sorting_data-generator`](https://github.com/VBVR-DataFactory/O-65_animal_size_sorting_data-generator) |

</details>

### Abstraction &mdash; 33 tasks

Distillation of generalizable knowledge from particular experiences.

<details>
<summary><b>Training Set</b> (10 tasks)</summary>

| ID | Task | Repository |
|:--|:--|:--|
| G-7 | Return To Correct Bin | [`G-7_return_to_correct_bin_data-generator`](https://github.com/VBVR-DataFactory/G-7_return_to_correct_bin_data-generator) |
| G-26 | Maintain Object Identity | [`G-26_maintain_object_identity_different_objects_data-generator`](https://github.com/VBVR-DataFactory/G-26_maintain_object_identity_different_objects_data-generator) |
| G-37 | Symmetry Random | [`G-37_symmetry_random_data-generator`](https://github.com/VBVR-DataFactory/G-37_symmetry_random_data-generator) |
| G-38 | Symmetry Shape | [`G-38_symmetry_shape_data-generator`](https://github.com/VBVR-DataFactory/G-38_symmetry_shape_data-generator) |
| G-44 | BFS | [`G-44_bfs_data-generator`](https://github.com/VBVR-DataFactory/G-44_bfs_data-generator) |
| G-49 | Complete Missing Contour Segments | [`G-49_complete_missing_contour_segments_data-generator`](https://github.com/VBVR-DataFactory/G-49_complete_missing_contour_segments_data-generator) |
| G-133 | Select Next Figure (Decreasing Size) | [`G-133_select_next_figure_decreasing_size_sequence_data-generator`](https://github.com/VBVR-DataFactory/G-133_select_next_figure_decreasing_size_sequence_data-generator) |
| O-7 | Shape Color Change | [`O-7_shape_color_change_data-generator`](https://github.com/VBVR-DataFactory/O-7_shape_color_change_data-generator) |
| O-8 | Shape Rotation | [`O-8_shape_rotation_data-generator`](https://github.com/VBVR-DataFactory/O-8_shape_rotation_data-generator) |
| O-66 | Animal Color Sorting | [`O-66_animal_color_sorting_data-generator`](https://github.com/VBVR-DataFactory/O-66_animal_color_sorting_data-generator) |

</details>

<details>
<summary><b>In-Domain Test Set</b> (15 tasks)</summary>

| ID | Task | Repository |
|:--|:--|:--|
| G-29 | Chart Extreme With Data | [`G-29_chart_extreme_with_data_data-generator`](https://github.com/VBVR-DataFactory/G-29_chart_extreme_with_data_data-generator) |
| G-41 | Grid Highest Cost | [`G-41_grid_highest_cost_data-generator`](https://github.com/VBVR-DataFactory/G-41_grid_highest_cost_data-generator) |
| G-51 | Predict Next Color | [`G-51_predict_next_color_data-generator`](https://github.com/VBVR-DataFactory/G-51_predict_next_color_data-generator) |
| G-131 | Select Next Figure (Increasing Size) | [`G-131_select_next_figure_increasing_size_sequence_data-generator`](https://github.com/VBVR-DataFactory/G-131_select_next_figure_increasing_size_sequence_data-generator) |
| G-134 | Select Next Figure (Large-Small Alternating) | [`G-134_select_next_figure_large_small_alternating_sequence_data-generator`](https://github.com/VBVR-DataFactory/G-134_select_next_figure_large_small_alternating_sequence_data-generator) |
| O-10 | Shape Outline Fill | [`O-10_shape_outline_fill_data-generator`](https://github.com/VBVR-DataFactory/O-10_shape_outline_fill_data-generator) |
| O-12 | Shape Color Then Scale | [`O-12_shape_color_then_scale_data-generator`](https://github.com/VBVR-DataFactory/O-12_shape_color_then_scale_data-generator) |
| O-13 | Shape Outline Then Move | [`O-13_shape_outline_then_move_data-generator`](https://github.com/VBVR-DataFactory/O-13_shape_outline_then_move_data-generator) |
| O-14 | Shape Scale Then Outline | [`O-14_shape_scale_then_outline_data-generator`](https://github.com/VBVR-DataFactory/O-14_shape_scale_then_outline_data-generator) |
| O-21 | Construction Blueprint | [`O-21_construction_blueprint_data-generator`](https://github.com/VBVR-DataFactory/O-21_construction_blueprint_data-generator) |
| O-29 | Ball Color | [`O-29_ballcolor_data-generator`](https://github.com/VBVR-DataFactory/O-29_ballcolor_data-generator) |
| O-30 | Bookshelf | [`O-30_bookshelf_data-generator`](https://github.com/VBVR-DataFactory/O-30_bookshelf_data-generator) |
| O-37 | Light Sequence | [`O-37_light_sequence_data-generator`](https://github.com/VBVR-DataFactory/O-37_light_sequence_data-generator) |
| O-45 | Sequence Completion | [`O-45_sequence_completion_data-generator`](https://github.com/VBVR-DataFactory/O-45_sequence_completion_data-generator) |
| O-47 | Sliding Puzzle | [`O-47_sliding_puzzle_data-generator`](https://github.com/VBVR-DataFactory/O-47_sliding_puzzle_data-generator) |

</details>

<details>
<summary><b>Out-of-Domain Test Set</b> (8 tasks)</summary>

| ID | Task | Repository |
|:--|:--|:--|
| G-135 | Select Next Figure (Small-Large Alternating) | [`G-135_select_next_figure_small_large_alternating_sequence_data-generator`](https://github.com/VBVR-DataFactory/G-135_select_next_figure_small_large_alternating_sequence_data-generator) |
| G-193 | Draw Next Sized Shape | [`G-193_draw_next_sized_shape_data-generator`](https://github.com/VBVR-DataFactory/G-193_draw_next_sized_shape_data-generator) |
| O-9 | Shape Scaling | [`O-9_shape_scaling_data-generator`](https://github.com/VBVR-DataFactory/O-9_shape_scaling_data-generator) |
| O-11 | Shape Color Then Move | [`O-11_shape_color_then_move_data-generator`](https://github.com/VBVR-DataFactory/O-11_shape_color_then_move_data-generator) |
| O-43 | Object Subtraction | [`O-43_object_subtraction_data-generator`](https://github.com/VBVR-DataFactory/O-43_object_subtraction_data-generator) |
| O-49 | Symmetry Completion | [`O-49_symmetry_completion_data-generator`](https://github.com/VBVR-DataFactory/O-49_symmetry_completion_data-generator) |
| O-54 | Control Panel | [`O-54_control_panel_data-generator`](https://github.com/VBVR-DataFactory/O-54_control_panel_data-generator) |
| O-56 | Raven | [`O-56_raven_data-generator`](https://github.com/VBVR-DataFactory/O-56_raven_data-generator) |

</details>

### Transformation &mdash; 29 tasks

Manipulation and synthesis of mental representations.

<details>
<summary><b>Training Set</b> (9 tasks)</summary>

| ID | Task | Repository |
|:--|:--|:--|
| G-1 | Object Trajectory | [`G-1_object_trajectory_data-generator`](https://github.com/VBVR-DataFactory/G-1_object_trajectory_data-generator) |
| G-2 | Reorder Objects | [`G-2_reorder_objects_data-generator`](https://github.com/VBVR-DataFactory/G-2_reorder_objects_data-generator) |
| G-6 | Resize Object | [`G-6_resize_object_data-generator`](https://github.com/VBVR-DataFactory/G-6_resize_object_data-generator) |
| G-11 | Handle Object Reappearance | [`G-11_handle_object_reappearance_data-generator`](https://github.com/VBVR-DataFactory/G-11_handle_object_reappearance_data-generator) |
| G-34 | Object Packing | [`G-34_object_packing_data-generator`](https://github.com/VBVR-DataFactory/G-34_object_packing_data-generator) |
| G-36 | Multiple Occlusions Horizontal | [`G-36_multiple_occlusions_horizontal_data-generator`](https://github.com/VBVR-DataFactory/G-36_multiple_occlusions_horizontal_data-generator) |
| G-40 | Combined Objects Spinning | [`G-40_combined_objects_spinning_data-generator`](https://github.com/VBVR-DataFactory/G-40_combined_objects_spinning_data-generator) |
| G-50 | Suppress Spurious Edges | [`G-50_suppress_spurious_edges_data-generator`](https://github.com/VBVR-DataFactory/G-50_suppress_spurious_edges_data-generator) |
| O-4 | Symbol Substitution | [`O-4_symbol_substitution_data-generator`](https://github.com/VBVR-DataFactory/O-4_symbol_substitution_data-generator) |

</details>

<details>
<summary><b>In-Domain Test Set</b> (7 tasks)</summary>

| ID | Task | Repository |
|:--|:--|:--|
| G-8 | Track Object Movement | [`G-8_track_object_movement_data-generator`](https://github.com/VBVR-DataFactory/G-8_track_object_movement_data-generator) |
| G-21 | Multiple Occlusions Vertical | [`G-21_multiple_occlusions_vertical_data-generator`](https://github.com/VBVR-DataFactory/G-21_multiple_occlusions_vertical_data-generator) |
| G-25 | Separate Object Spinning | [`G-25_seperate_object_spinning_data-generator`](https://github.com/VBVR-DataFactory/G-25_seperate_object_spinning_data-generator) |
| G-194 | Construct Concentric Ring | [`G-194_construct_concentric_ring_data-generator`](https://github.com/VBVR-DataFactory/G-194_construct_concentric_ring_data-generator) |
| O-32 | Rolling Ball | [`O-32_rolling_ball_data-generator`](https://github.com/VBVR-DataFactory/O-32_rolling_ball_data-generator) |
| O-36 | Grid Shift | [`O-36_grid_shift_data-generator`](https://github.com/VBVR-DataFactory/O-36_grid_shift_data-generator) |
| O-44 | Rotation Puzzle | [`O-44_rotation_puzzle_data-generator`](https://github.com/VBVR-DataFactory/O-44_rotation_puzzle_data-generator) |

</details>

<details>
<summary><b>Out-of-Domain Test Set</b> (13 tasks)</summary>

| ID | Task | Repository |
|:--|:--|:--|
| G-24 | Separate Objects No Spin | [`G-24_separate_objects_no_spin_data-generator`](https://github.com/VBVR-DataFactory/G-24_separate_objects_no_spin_data-generator) |
| G-240 | Add Borders To Unbordered Shapes | [`G-240_add_borders_to_unbordered_shapes_data-generator`](https://github.com/VBVR-DataFactory/G-240_add_borders_to_unbordered_shapes_data-generator) |
| O-5 | Symbol Deletion | [`O-5_symbol_deletion_data-generator`](https://github.com/VBVR-DataFactory/O-5_symbol_deletion_data-generator) |
| O-6 | 2D Geometric Transformation | [`O-6_2d_geometric_transformation_data-generator`](https://github.com/VBVR-DataFactory/O-6_2d_geometric_transformation_data-generator) |
| O-22 | Construction Stack | [`O-22_construction_stack_data-generator`](https://github.com/VBVR-DataFactory/O-22_construction_stack_data-generator) |
| O-27 | Move 2 Objects To 2 Targets | [`O-27_move_2_object_to_2_target_data-generator`](https://github.com/VBVR-DataFactory/O-27_move_2_object_to_2_target_data-generator) |
| O-46 | Shape Sorter | [`O-46_shape_sorter_data-generator`](https://github.com/VBVR-DataFactory/O-46_shape_sorter_data-generator) |
| O-58 | Symbol Delete | [`O-58_symbol_delete_data-generator`](https://github.com/VBVR-DataFactory/O-58_symbol_delete_data-generator) |
| O-59 | Symbol Insert | [`O-59_symbol_insert_data-generator`](https://github.com/VBVR-DataFactory/O-59_symbol_insert_data-generator) |
| O-60 | Symbol Substitute | [`O-60_symbol_substitute_data-generator`](https://github.com/VBVR-DataFactory/O-60_symbol_substitute_data-generator) |
| O-61 | Symbol Edit | [`O-61_symbol_edit_data-generator`](https://github.com/VBVR-DataFactory/O-61_symbol_edit_data-generator) |
| O-64 | Animal Matching | [`O-64_animal_matching_data-generator`](https://github.com/VBVR-DataFactory/O-64_animal_matching_data-generator) |
| O-85 | 2D Object Rotation | [`O-85_2d_object_rotation_data-generator`](https://github.com/VBVR-DataFactory/O-85_2d_object_rotation_data-generator) |

</details>

### Knowledge &mdash; 23 tasks

Propositional truths, either learned or innate.

<details>
<summary><b>Training Set</b> (9 tasks)</summary>

| ID | Task | Repository |
|:--|:--|:--|
| G-27 | Read Chart Data (Semantic Comprehension) | [`G-27_read_the_chart_data_semantic_comprehension_data-generator`](https://github.com/VBVR-DataFactory/G-27_read_the_chart_data_semantic_comprehension_data-generator) |
| G-30 | Chart Extreme Without Data | [`G-30_chart_extreme_without_data_data-generator`](https://github.com/VBVR-DataFactory/G-30_chart_extreme_without_data_data-generator) |
| G-35 | Hit Target After Bounce | [`G-35_hit_target_after_bounce_data-generator`](https://github.com/VBVR-DataFactory/G-35_hit_target_after_bounce_data-generator) |
| G-48 | Multiple Bounces | [`G-48_multiple_bounces_data-generator`](https://github.com/VBVR-DataFactory/G-48_multiple_bounces_data-generator) |
| G-162 | Locate Twelve O'Clock Arrows | [`G-162_locate_twelve_o_clock_arrows_data-generator`](https://github.com/VBVR-DataFactory/G-162_locate_twelve_o_clock_arrows_data-generator) |
| G-163 | Identify One And Nine | [`G-163_identify_one_and_nine_data-generator`](https://github.com/VBVR-DataFactory/G-163_identify_one_and_nine_data-generator) |
| G-200 | Circle Maximum Value | [`G-200_circle_maximum_value_data-generator`](https://github.com/VBVR-DataFactory/G-200_circle_maximum_value_data-generator) |
| O-3 | Symbol Reordering | [`O-3_symbol_reordering_data-generator`](https://github.com/VBVR-DataFactory/O-3_symbol_reordering_data-generator) |
| O-87 | Fluid Diffusion Reasoning | [`O-87_fluid_diffusion_reasoning_data-generator`](https://github.com/VBVR-DataFactory/O-87_fluid_diffusion_reasoning_data-generator) |

</details>

<details>
<summary><b>In-Domain Test Set</b> (9 tasks)</summary>

| ID | Task | Repository |
|:--|:--|:--|
| O-15 | Ball Bounces Given Time | [`O-15_ball_bounces_given_time_data-generator`](https://github.com/VBVR-DataFactory/O-15_ball_bounces_given_time_data-generator) |
| O-18 | Glass Refraction | [`O-18_glass_refraction_data-generator`](https://github.com/VBVR-DataFactory/O-18_glass_refraction_data-generator) |
| O-19 | Mirror Reflection | [`O-19_mirror_reflection_data-generator`](https://github.com/VBVR-DataFactory/O-19_mirror_reflection_data-generator) |
| O-23 | Domino Chain Branch Path Prediction | [`O-23_domino_chain_branch_path_prediction_data-generator`](https://github.com/VBVR-DataFactory/O-23_domino_chain_branch_path_prediction_data-generator) |
| O-24 | Domino Chain Gap Analysis | [`O-24_domino_chain_gap_analysis_data-generator`](https://github.com/VBVR-DataFactory/O-24_domino_chain_gap_analysis_data-generator) |
| O-34 | Dot To Dot Task | [`O-34_dot_to_dot_task_data-generator`](https://github.com/VBVR-DataFactory/O-34_dot_to_dot_task_data-generator) |
| O-52 | Traffic Light | [`O-52_traffic_light_data-generator`](https://github.com/VBVR-DataFactory/O-52_traffic_light_data-generator) |
| O-53 | Clock | [`O-53_clock_data-generator`](https://github.com/VBVR-DataFactory/O-53_clock_data-generator) |
| O-75 | Communicating Vessels | [`O-75_communicating_vessels_data-generator`](https://github.com/VBVR-DataFactory/O-75_communicating_vessels_data-generator) |

</details>

<details>
<summary><b>Out-of-Domain Test Set</b> (5 tasks)</summary>

| ID | Task | Repository |
|:--|:--|:--|
| G-160 | Circle Largest Numerical Value | [`G-160_circle_largest_numerical_value_data-generator`](https://github.com/VBVR-DataFactory/G-160_circle_largest_numerical_value_data-generator) |
| G-217 | Circle Central Dot | [`G-217_circle_central_dot_data-generator`](https://github.com/VBVR-DataFactory/G-217_circle_central_dot_data-generator) |
| G-247 | Identify Chinese Character | [`G-247_identify_chinese_character_data-generator`](https://github.com/VBVR-DataFactory/G-247_identify_chinese_character_data-generator) |
| G-273 | High Density Liquid | [`G-273_high_density_liquid_data-generator`](https://github.com/VBVR-DataFactory/G-273_high_density_liquid_data-generator) |
| O-62 | Gravity Physics | [`O-62_gravity_physics_data-generator`](https://github.com/VBVR-DataFactory/O-62_gravity_physics_data-generator) |

</details>

### Spatiality &mdash; 20 tasks

Representation of places and geometric relationships.

<details>
<summary><b>Training Set</b> (7 tasks)</summary>

| ID | Task | Repository |
|:--|:--|:--|
| G-12 | Grid Obtaining Award | [`G-12_grid_obtaining_award_data-generator`](https://github.com/VBVR-DataFactory/G-12_grid_obtaining_award_data-generator) |
| G-14 | Grid Color Sequence | [`G-14_grid_color_sequence_data-generator`](https://github.com/VBVR-DataFactory/G-14_grid_color_sequence_data-generator) |
| G-17 | Grid Avoid Red Block | [`G-17_grid_avoid_red_block_data-generator`](https://github.com/VBVR-DataFactory/G-17_grid_avoid_red_block_data-generator) |
| G-32 | Undirected Graph Navigation | [`G-32_undirected_graph_navigation_data-generator`](https://github.com/VBVR-DataFactory/G-32_undirected_graph_navigation_data-generator) |
| G-33 | Visual Jenga | [`G-33_visual_jenga_data-generator`](https://github.com/VBVR-DataFactory/G-33_visual_jenga_data-generator) |
| G-46 | Find Keys And Open Doors | [`G-46_find_keys_and_open_doors_data-generator`](https://github.com/VBVR-DataFactory/G-46_find_keys_and_open_doors_data-generator) |
| O-83 | Planar Warp Verification | [`O-83_planar_warp_verification_data-generator`](https://github.com/VBVR-DataFactory/O-83_planar_warp_verification_data-generator) |

</details>

<details>
<summary><b>In-Domain Test Set</b> (8 tasks)</summary>

| ID | Task | Repository |
|:--|:--|:--|
| G-13 | Grid Number Sequence | [`G-13_grid_number_sequence_data-generator`](https://github.com/VBVR-DataFactory/G-13_grid_number_sequence_data-generator) |
| G-15 | Grid Avoid Obstacles | [`G-15_grid_avoid_obstacles_data-generator`](https://github.com/VBVR-DataFactory/G-15_grid_avoid_obstacles_data-generator) |
| G-16 | Grid Go Through Block | [`G-16_grid_go_through_block_data-generator`](https://github.com/VBVR-DataFactory/G-16_grid_go_through_block_data-generator) |
| G-18 | Grid Shortest Path | [`G-18_grid_shortest_path_data-generator`](https://github.com/VBVR-DataFactory/G-18_grid_shortest_path_data-generator) |
| G-31 | Directed Graph Navigation | [`G-31_directed_graph_navigation_data-generator`](https://github.com/VBVR-DataFactory/G-31_directed_graph_navigation_data-generator) |
| G-45 | Key Door Matching | [`G-45_key_door_matching_data-generator`](https://github.com/VBVR-DataFactory/G-45_key_door_matching_data-generator) |
| O-25 | LEGO Construction Assembly | [`O-25_LEGO_construction_assembly_data-generator`](https://github.com/VBVR-DataFactory/O-25_LEGO_construction_assembly_data-generator) |
| O-55 | Rotation | [`O-55_rotation_data-generator`](https://github.com/VBVR-DataFactory/O-55_rotation_data-generator) |

</details>

<details>
<summary><b>Out-of-Domain Test Set</b> (5 tasks)</summary>

| ID | Task | Repository |
|:--|:--|:--|
| G-47 | Multiple Keys For One Door | [`G-47_multiple_keys_for_one_door_data-generator`](https://github.com/VBVR-DataFactory/G-47_multiple_keys_for_one_door_data-generator) |
| G-140 | Locate Topmost Unobscured Figure | [`G-140_locate_topmost_unobscured_figure_data-generator`](https://github.com/VBVR-DataFactory/G-140_locate_topmost_unobscured_figure_data-generator) |
| G-219 | Select Leftmost Shape | [`G-219_select_leftmost_shape_data-generator`](https://github.com/VBVR-DataFactory/G-219_select_leftmost_shape_data-generator) |
| G-221 | Outline Innermost Square | [`G-221_outline_innermost_square_data-generator`](https://github.com/VBVR-DataFactory/G-221_outline_innermost_square_data-generator) |
| O-39 | Maze | [`O-39_maze_data-generator`](https://github.com/VBVR-DataFactory/O-39_maze_data-generator) |

</details>

---

## Contributing

1. **Fork** [`template-data-generator`](https://github.com/VBVR-DataFactory/template-data-generator)
2. **Design** your task targeting one of the five cognitive faculties
3. **Implement** a parameterized generator that produces `first_frame.png`, `prompt.txt`, `final_frame.png`, and `ground_truth.mp4`
4. **Submit** for review against six quality criteria: information sufficiency, deterministic solvability, video dependency, visual clarity, parametric diversity (10,000+ instances), and technical feasibility

---

## Community

- **Website**: [video-reason.com](https://video-reason.com/)
- **Slack**: [Join our workspace](https://join.slack.com/t/vm-dataset/shared_invite/zt-3mdb2lkye-lm7ZC4OGxxRRMEi1M65hKQ)
- **HuggingFace**: [VideoReason](https://huggingface.co/VideoReason)
- **Contact**: [hokinxqdeng@gmail.com](mailto:hokinxqdeng@gmail.com)

---

## Citation

```bibtex
@article{vbvr2026,
  title={A Very Big Video Reasoning Suite},
  author={Wang, Maijunxian and Wang, Ruisi and Lin, Juyi and Ji, Ran and Wiedemer, Thaddäus and Gao, Qingying and Luo, Dezhi and Qian, Yaoyao and Huang, Lianyu and Hong, Zelong and Ge, Jiahui and Ma, Qianli and He, Hang and Zhou, Yifan and Guo, Lingzi and Mei, Lantao and Li, Jiachen and Xing, Hanwen and Zhao, Tianqi and Yu, Fengyuan and Xiao, Weihang and Jiao, Yizheng and Hou, Jianheng and Zhang, Danyang and Xu, Pengcheng and Zhong, Boyang and Zhao, Zehong and Fang, Gaoyun and Kitaoka, John and Xu, Yile and Xu, Hua and Blacutt, Kenton and Nguyen, Tin and Song, Siyuan and Sun, Haoran and Wen, Shaoyue and He, Linyang and Wang, Runming and Wang, Yanzhi and Yang, Mengyue and Ma, Ziqiao and Millière, Raphaël and Shi, Freda and Vasconcelos, Nuno and Khashabi, Daniel and Yuille, Alan and Du, Yilun and Liu, Ziming and Lin, Dahua and Liu, Ziwei and Kumar, Vikash and Li, Yijiang and Yang, Lei and Cai, Zhongang and Deng, Hokin},
  year={2026}
}
```

---

<div align="center">
  <sub>A collaborative effort by 50+ researchers from 30+ institutions worldwide &mdash; MIT License</sub>
</div>
