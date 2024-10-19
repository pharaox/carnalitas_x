# Files

## Vanilla Files and Objects

### Explicit

* `common/character_interactions/00_perk_interactions.txt`
  * `demand_payment_interaction`
* `common/character_interactions/00_prison_interactions.txt`
  * `release_from_prison_interaction`
* `common/character_interactions/00_religious_interactions.txt`
  * `ask_for_conversion_courtier_interaction`
* `common/council_positions/00_council_positions.txt`
  * Entire file
* `common/court_positions/types/00_court_positions.txt`
  * Entire file
* `common/scripted_effects/00_holy_order_effects.txt`
  * `release_as_executioner_effect`
* `common/scripted_effects/00_prison_effects.txt`
  * `prisoner_of_war_capture_effect`
  * `imprison_tyranny_effect`
* `common/scripted_modifiers/00_scheme_scripted_modifiers.txt`
  * `ai_agent_join_chance_hostile_taboo_modifier`
  * `ai_agent_join_chance_hostile_grievous_modifier`
* `common/scripted_triggers/00_court_position_triggers.txt`
  * `court_position_does_not_already_have_a_job_trigger`
* `common/scripted_triggers/00_courtier_guest_management_triggers.txt`
  * `can_recruit_character_to_court_trigger`
* `common/scripted_triggers/00_interaction_triggers.txt`
  * `kick_from_court_validity_trigger`
* `common/scripted_triggers/00_secret_type_triggers.txt`
  * `secret_lover_is_valid_trigger`
* `common/scripted_triggers/00_war_and_peace_triggers.txt`
  * `desirable_for_capture_trigger`

### Implicit

* `common/scripted_triggers/00_court_position_triggers.txt`
  * Court position validity triggers
    * => `common/scripted_triggers/carnx_court_position_triggers.txt`
* `common/on_action/child_birth_on_actions.txt`
  * `on_birth_child`
    * => `common/scripted_effects/carnx_child_birth_effects.txt`
* `common/scripted_effects/00_prison_effects.txt`
  * `execute_prisoner_effect`
    * => `common/scripted_effects/carnx_slave_effects.txt`
      * `carnx_enslave_effect`

## Carnalitas Files and Objects

### Explicit

* `common/character_interactions/*.txt`
  * `carn_buy_slave_directly_interaction`
  * `carn_demand_free_illegal_slaves_interaction`
  * `carn_enslave_interaction`
  * `carn_free_slave_interaction`
  * `carn_seize_slave_interaction`
  * `carn_sell_slave_interaction`
* `common/important_actions/action_carn_can_demand_free_illegal_slaves_interaction.txt`
  * Entire file
* `common/on_action/carn_slave_on_actions.txt`
  * Entire file
* `common/script_values/carn_slave_values.txt`
  * `carn_scope_buyer_current_gold_value`
* `common/script_values/carn_sex_pregnancy_chance.txt`
  * `carn_sex_pregnancy_chance`
* `common/scripted_effects/carn_slave_effects.txt`
  * `carn_enslave_effect`
  * `carn_free_slave_effect`
  * `carn_free_illegal_slaves_effect`
  * `carn_free_slave_interaction_effect`
  * `carn_buy_slave_effect`
* `common/scripted_triggers/carn_gender_triggers.txt`
  * `carn_gender_can_impregnate_trigger`
  * `carn_possible_pregnancy_after_sex_with_character_trigger`
* `common/scripted_triggers/carn_sex_interaction_triggers.txt`
  * `carn_relationship_allows_free_sex_trigger`

## Miscellaneous

### Court Positions

* For new councillor or court positions that could be held by slaves:
  * Adapt the position itself and all effects, modifiers, and triggers.
  * Consider updating `carnx_vanilla_court_position_traits_character_value` for aptitude traits.
