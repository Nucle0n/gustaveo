
# Gustaveo - Functional Specifications

## Document information

| Property | Value |
|----------|-------|
| Project | Gustaveo |
| Organization | NSS Labs |
| Document version | 0.1.0 |
| Status | Draft |
| Created | 2026-11-27 |

## 1. Project overview

Gustaveo is an AI-powered culinary assistant designed to help
users discover, personalize and generate recipes based on their
individual preferences, available ingredients and cooking
constraints.

The application provides an intuitive and interactive experience
through a guided selection interface, without requiring users
to write complex prompts or have prior experience with
artificial intelligence tools.

Gustaveo is designed as a general-purpose culinary application,
supporting multiple dietary preferences and cooking styles.

## 2. Background and motivation

The project originated from the difficulty of finding creative,
appetizing and personalized recipes when cooking with unfamiliar
ingredients or dietary restrictions.

Traditional recipe websites often require users to browse
large collections of predefined recipes that may not fully
match their preferences, available ingredients or equipment.

Conversational AI can provide personalized culinary suggestions,
but requires users to formulate their requests manually.

Gustaveo aims to combine the flexibility of artificial
intelligence with the simplicity of a dedicated culinary
interface.

## 3. Problem statement

Users frequently encounter difficulties when deciding what
to cook.

These difficulties may include:

- Lack of culinary inspiration.
- Unfamiliarity with specific dietary requirements.
- Limited available ingredients.
- Limited cooking equipment.
- Time and budget constraints.
- Difficulty adapting existing recipes.
- Repetitive meal choices.
- Difficulty finding recipes that satisfy multiple preferences.

Gustaveo addresses these challenges by generating personalized
culinary suggestions based on structured user inputs.

## 4. Project objectives

### 4.1 Primary objectives

- Simplify the discovery of personalized recipes.
- Provide culinary inspiration through artificial intelligence.
- Generate recipes adapted to user preferences and constraints.
- Support multiple dietary preferences.
- Provide clear and actionable cooking instructions.
- Offer an intuitive, accessible and responsive interface.
- Minimize the need for manual prompt writing.

### 4.2 Secondary objectives

- Encourage culinary creativity and experimentation.
- Help users discover unfamiliar ingredients and cooking methods.
- Reduce food waste by using available ingredients.
- Simplify grocery shopping and meal preparation.
- Provide a foundation for future meal planning features.

## 5. Target audience

Gustaveo is intended for a broad audience, including:

- Home cooks looking for culinary inspiration.
- Beginners with limited cooking experience.
- Experienced cooks looking for creative ideas.
- People following specific dietary preferences.
- People cooking for others with different dietary requirements.
- Users with limited time, ingredients or cooking equipment.
- Users interested in discovering new cuisines.

The application should remain accessible regardless of the
user's culinary experience or familiarity with artificial
intelligence.

## 6. Functional requirements

The functional requirements defined in this section
describe the overall product vision.

Their implementation priority and applicability
to the MVP shall be determined by Section 10.

Requirements associated with deferred functionality
shall become applicable when the corresponding
functionality is implemented.

Mandatory food safety, security and privacy
requirements shall apply to all implemented
functionality, regardless of release scope.

### 6.1 Food allergies and intolerances

Food allergy and intolerance management is a mandatory
food safety requirement of Gustaveo.

#### FR-001 - Allergen selection

The application shall provide a multiple-selection interface
covering the 14 regulated allergen categories defined in
Annex II of Regulation (EU) No 1169/2011.

#### FR-002 - Custom exclusions

Users shall be able to specify additional food allergies,
intolerances and specific substances to exclude.

Allergies and intolerances shall be distinguishable from
general dietary preferences.

#### FR-003 - Constraint prioritization

Food safety constraints shall take precedence over dietary
preferences, ingredient preferences and culinary styles.

The application shall never silently relax these constraints.

#### FR-004 - Conflict detection

The application shall detect conflicting user selections
before submitting a recipe generation request.

#### FR-005 - Allergen-aware generation

All declared food safety constraints shall be included in
both recipe suggestion and detailed recipe generation
requests.

#### FR-006 - Independent validation

Generated ingredients shall be checked independently
of the AI generation process against an allergen reference
dataset.

Known allergen derivatives and compound ingredients shall
be considered during validation.

Conflicting or unverifiable recipes shall not be presented
as compatible with the user's allergies.

#### FR-007 - Allergen information

Generated recipes shall display identified allergens
and relevant ingredient-specific warnings.

#### FR-008 - Food safety disclaimer

The application shall clearly communicate the limitations
of automated allergen identification.

Users shall be reminded to verify product labels,
ingredient composition and cross-contamination risks.

The application shall not guarantee that any generated
recipe is allergen-free or medically safe.

#### FR-009 - Constraint preservation

Food safety constraints shall remain active during recipe
regeneration, customization, ingredient substitution
and serving size adjustments.

#### Regulatory reference

- [Regulation (EU) No 1169/2011 - Annex II](https://eur-lex.europa.eu/eli/reg/2011/1169/oj)

### 6.2 Internationalization and localization

Gustaveo shall be designed with internationalization (i18n)
and localization (l10n) support from the beginning of
the development process.

#### FR-010 - Language selection

Users shall be able to select their preferred application
language.

#### FR-011 - Language switching

Users shall be able to change the interface language
without losing their current selections or application state.

#### FR-012 - Translation management

All static user-facing text shall be managed through
dedicated translation resources.

User-facing text shall not be hardcoded into application
logic.

#### FR-013 - Language-independent data

Internal identifiers, application data and validation
rules shall remain independent of the selected language.

#### FR-014 - Localized recipe generation

AI-generated recipe suggestions and detailed recipes
shall be generated in the user's selected language.

#### FR-015 - Regional formatting

The application shall support locale-aware formatting
of numbers, quantities and measurement units.

Language and measurement system preferences shall remain
independent.

#### FR-016 - Localized food safety information

Allergen names, food safety warnings and disclaimers
shall be available in every officially supported language.

Allergen validation shall remain independent of the
selected language.

#### FR-017 - Language extensibility

Adding a new interface language shall not require
modifications to the core application logic.

#### FR-018 - Language fallback

The application shall provide a default language fallback
when a translation is unavailable.

Missing safety-critical translations shall be identified
and resolved before releasing a new language.

#### FR-019 - Language preference persistence

The application shall remember the user's selected
interface language between sessions when local
storage is available and permitted.

Unavailable persistent storage shall not prevent
language selection or core application usage.

### 6.3 Dietary preferences

Gustaveo shall support multiple dietary patterns,
nutritional preferences and additional dietary constraints.

The dietary preference system shall be extensible and
independent of the selected application language.

#### FR-020 - Primary dietary pattern

Users shall be able to select a primary dietary pattern
from a predefined list.

The application shall provide an unrestricted option
for users without specific dietary requirements.

#### FR-021 - Nutritional preferences

Users shall be able to select multiple optional
nutritional preferences.

Nutritional preferences shall be distinguishable from
mandatory dietary and food safety constraints.

#### FR-022 - Additional dietary constraints

The application shall support additional dietary
constraints independently of the primary dietary pattern.

#### FR-023 - Custom dietary requirements

Users shall be able to specify additional dietary
requirements through a dedicated input field.

Custom requirements shall not override existing
food safety constraints.

#### FR-024 - Dynamic option filtering

Available ingredient and recipe configuration options
shall dynamically adapt to the selected dietary pattern
and declared food safety constraints.

Known incompatible options shall be disabled or excluded
from the available selections.

#### FR-025 - Selection consistency

When a dietary pattern or constraint is modified,
the application shall revalidate existing selections.

Incompatible selections shall be clearly identified
and shall not be silently retained.

#### FR-026 - Dietary constraint preservation

Mandatory dietary constraints shall be preserved
throughout recipe suggestion, detailed recipe generation,
regeneration, customization and ingredient substitution.

#### FR-027 - Dietary compatibility validation

Generated recipes shall be checked for compatibility
with the selected mandatory dietary constraints.

Unverifiable dietary compatibility shall be clearly
communicated to the user.

The application shall not claim religious certification
or medical suitability that cannot be independently
verified.

#### FR-028 - Dietary pattern extensibility

Dietary patterns, nutritional preferences and their
compatibility rules shall be defined independently
of the core application logic.

Adding a new dietary pattern shall not require
a redesign of the application.

#### FR-029 - Optional preferences

Users shall be able to generate recipe suggestions
without specifying optional dietary or nutritional
preferences.

### 6.4 Ingredient selection and management

Gustaveo shall provide a flexible ingredient selection
system allowing users to express ingredient preferences,
availability and mandatory exclusions.

Ingredient selection shall remain optional unless required
by a specific recipe generation mode.

#### FR-030 - Ingredient catalog

The application shall provide a categorized catalog
of commonly used culinary ingredients.

Ingredients may belong to multiple categories.

#### FR-031 - Ingredient search

Users shall be able to search for ingredients
within the ingredient catalog.

Ingredient search shall support the selected
application language.

#### FR-032 - Multiple ingredient selection

Users shall be able to select multiple ingredients
across different ingredient categories.

#### FR-033 - Ingredient selection modes

The application shall distinguish between the following
ingredient selection modes:

- Required ingredients.
- Preferred ingredients.
- Available ingredients.
- Avoided ingredients.
- Excluded ingredients.

Required and excluded ingredients shall be treated
as mandatory constraints.

Preferred and avoided ingredients shall be treated
as flexible preferences.

Ingredient availability shall be managed independently
of ingredient preferences.

#### FR-034 - Custom ingredients

Users shall be able to specify ingredients that are
not present in the predefined ingredient catalog.

Custom ingredients shall be subject to the same
compatibility and food safety validation rules.

#### FR-035 - Ingredient compatibility

Ingredient selections shall be validated against
the selected dietary pattern, declared allergies,
intolerances and mandatory exclusions.

Food safety constraints shall take precedence over
all ingredient selections.

#### FR-036 - Ingredient quantities

Users shall be able to optionally specify available
ingredient quantities and measurement units.

Providing quantities shall not be mandatory.

#### FR-037 - Ingredient availability modes

The application shall support different levels
of ingredient availability constraints:

- Flexible: additional ingredients may be suggested.
- Preferred: available ingredients shall be prioritized.
- Strict: only declared available ingredients may be used.

The selected mode shall be respected throughout
the recipe generation process.

#### FR-038 - Ingredient selection consistency

The application shall detect conflicting ingredient
selections and clearly inform the user.

Mandatory constraints shall not be silently removed
or relaxed.

#### FR-039 - Ingredient selection summary

The application shall provide a clear summary
of selected ingredients, preferences and exclusions.

Users shall be able to modify or remove individual
selections before generating recipes.

#### FR-040 - Ingredient catalog extensibility

The ingredient catalog, categories, localized names
and compatibility metadata shall be maintained
independently of the core application logic.

Adding new ingredients or categories shall not
require a redesign of the application.

#### FR-041 - Missing ingredient identification

Generated recipes shall identify ingredients
that are not included in the user's declared
available ingredients, when availability
information has been provided.

#### FR-042 - Optional ingredient configuration

Users shall be able to generate recipe suggestions
without selecting specific ingredients.

In this case, ingredient selection shall be delegated
to the AI within the applicable dietary, food safety
and cooking constraints.

### 6.5 Cooking preferences and constraints

Gustaveo shall allow users to configure recipe generation
according to their cooking environment, available resources,
personal preferences and practical constraints.

#### FR-043 - Serving size

Users shall be able to specify the number of servings
required for the generated recipe.

Ingredient quantities shall be adapted accordingly.

#### FR-044 - Time constraints

Users shall be able to specify a maximum total
recipe duration.

The application shall distinguish between:

- Preparation time.
- Cooking time.
- Resting and waiting time.
- Total elapsed time.

Total duration shall account for sequential
and parallel preparation activities.

#### FR-045 - Cooking difficulty

Users shall be able to specify their preferred
cooking difficulty level.

Recipe instructions and cooking techniques shall
be adapted to the selected difficulty level.

#### FR-046 - Budget preferences

Users shall be able to specify a qualitative
budget preference.

Estimated costs shall not be presented as
guaranteed or verified prices.

#### FR-047 - Available cooking equipment

Users shall be able to select multiple available
cooking appliances and equipment.

The application shall distinguish between unspecified
equipment availability and explicitly unavailable
equipment.

Generated recipes shall respect declared equipment
limitations.

#### FR-048 - Cooking method preferences

Users shall be able to select multiple preferred
cooking methods.

Available cooking methods shall be compatible
with the declared cooking equipment.

#### FR-049 - Dish categories

Users shall be able to select one or more
preferred dish categories.

Dish category selection shall remain optional.

#### FR-050 - Culinary styles

Users shall be able to select multiple culinary
style preferences.

Culinary styles shall remain independent of
dietary patterns and dish categories.

#### FR-051 - Culinary origins

Users shall be able to select multiple culinary
origins or regional cuisine preferences.

The application shall support creative combinations
of culinary traditions.

#### FR-052 - Meal occasions

Users shall be able to specify the intended
occasion or context of the meal.

Recipe suggestions shall account for the selected
occasion when provided.

#### FR-053 - Additional cooking instructions

Users shall be able to provide optional
free-text cooking instructions and preferences.

Additional instructions shall not override
mandatory dietary or food safety constraints.

#### FR-054 - Cooking constraint validation

The application shall validate cooking constraints
and detect incompatible selections before
submitting recipe generation requests.

Mandatory constraints shall not be silently relaxed.

#### FR-055 - Cooking constraint preservation

Mandatory cooking constraints shall remain active
throughout recipe suggestion, detailed recipe
generation, regeneration and customization.

#### FR-056 - Optional cooking configuration

Users shall be able to generate recipe suggestions
without specifying optional cooking preferences.

Reasonable default values shall be provided
where necessary.

#### FR-057 - Cooking configuration extensibility

Cooking equipment, cooking methods, dish categories,
culinary styles, culinary origins and meal occasions
shall be maintained independently of the core
application logic.

These configuration options shall support
internationalization and localization.

### 6.6 Recipe suggestions and presentation

Gustaveo shall generate concise and personalized recipe
suggestions before generating detailed recipes.

Recipe suggestions shall provide sufficient information
to allow users to make informed culinary choices.

#### FR-058 - Suggestion quantity

Users shall be able to specify the number of recipe
suggestions to generate within configurable limits.

A default suggestion quantity shall be provided.

#### FR-059 - Structured recipe suggestions

Each recipe suggestion shall contain:

- A unique identifier.
- A recipe title.
- A short culinary description.
- Main ingredients.
- A preliminary ingredient list.
- Estimated total duration.
- Estimated difficulty level.
- Qualitative budget estimation.
- Number of servings.
- Dietary compatibility information.
- Identified allergens and relevant warnings.
- Required cooking equipment.
- Missing ingredients, when applicable.
- Culinary origin or inspiration, when applicable.

The preliminary ingredient list shall identify
all intended ingredients required to evaluate
mandatory dietary and food safety constraints.

Ingredient quantities may remain unspecified
until detailed recipe generation.

Suggestions with insufficient ingredient
information shall not be presented as compatible
with mandatory food safety constraints.

#### FR-060 - Suggestion diversity

Generated recipe suggestions shall provide meaningful
culinary diversity whenever permitted by the selected
user constraints.

Unnecessary duplicates and minor variations of the
same recipe shall be avoided.

#### FR-061 - Suggestion validation

Recipe suggestions shall be validated against mandatory
food safety, dietary, ingredient and cooking constraints
before being presented to the user.

Suggestions with unresolved safety conflicts shall
not be presented as compatible.

#### FR-062 - Suggestion presentation

Recipe suggestions shall be presented through clear,
consistent and responsive visual components.

Essential recipe information shall remain accessible
on mobile devices.

#### FR-063 - Suggestion details

Users shall be able to access additional information
about a recipe suggestion without requesting the
generation of a complete recipe.

Safety-critical information shall remain clearly
visible and accessible.

#### FR-064 - Suggestion sorting

Users shall be able to sort generated recipe suggestions
according to available attributes, including:

- Estimated total duration.
- Estimated difficulty.
- Qualitative budget.

Sorting shall not require additional AI generation.

#### FR-065 - Recipe selection

Users shall be able to select an individual recipe
suggestion for detailed recipe generation.

The selected suggestion and all applicable constraints
shall be preserved during this process.

#### FR-066 - Individual suggestion regeneration

Users shall be able to regenerate an individual recipe
suggestion without replacing the other suggestions.

All mandatory constraints shall remain active.

#### FR-067 - Multiple suggestion regeneration

Users shall be able to request additional recipe
suggestions using their current configuration.

Previously generated suggestions shall be considered
to reduce unnecessary duplication.

#### FR-068 - Configuration preservation

Users shall be able to return to the recipe configuration
interface without losing their current selections.

#### FR-069 - Session suggestion history

The application shall preserve previously generated
recipe suggestions during the current session.

Users shall be able to access previous suggestions
without requiring additional AI generation.

#### FR-070 - Optional recipe illustrations

Recipe suggestions may include culinary illustrations.

The absence of an illustration shall not prevent
the presentation or selection of a recipe suggestion.

AI-generated illustrations shall be clearly identified
and shall not be presented as verified photographs
of the actual recipe outcome.

#### FR-071 - Generation feedback

The application shall provide clear feedback while
recipe suggestions are being generated and validated.

Users shall be informed of generation failures,
validation failures and unavailable results.

#### FR-072 - Unsatisfied constraints

When no valid recipe suggestion can be generated,
the application shall clearly inform the user.

The application may suggest adjustments to flexible
preferences but shall never automatically relax
mandatory constraints.

### 6.7 Detailed recipe generation and presentation

Gustaveo shall generate a complete and actionable recipe
from a previously selected recipe suggestion.

Detailed recipes shall remain consistent with the selected
suggestion and all applicable user constraints.

#### FR-073 - Detailed recipe generation

The application shall generate a complete recipe
from the selected recipe suggestion.

The original configuration and mandatory constraints
shall be preserved during detailed recipe generation.

#### FR-074 - Structured recipe content

Each detailed recipe shall contain:

- A unique identifier.
- A recipe title and description.
- Number of servings.
- Difficulty level.
- Preparation time.
- Cooking time.
- Resting and waiting time, when applicable.
- Total estimated duration.
- Qualitative budget estimation.
- A complete ingredient list.
- Ingredient quantities and measurement units.
- Required cooking equipment.
- Chronological preparation instructions.
- Identified allergens and food safety warnings.

Additional culinary information may be included
when relevant.

#### FR-075 - Ingredient quantities and units

Ingredient quantities shall be expressed using
clear and appropriate measurement units.

Quantities and units shall respect the user's
localization and measurement system preferences.

Approximate quantities shall be clearly identified.

#### FR-076 - Serving size adjustment

Users shall be able to modify the number of servings
of a generated recipe.

Ingredient quantities shall be adjusted appropriately.

Non-linear quantity adjustments, equipment capacity
and cooking time implications shall be considered.

Adjusted recipes shall remain compliant with all
mandatory constraints.

#### FR-077 - Ingredient checklist

Users shall be able to individually mark ingredients
as available, collected or prepared.

Checklist interactions shall not require additional
AI generation.

#### FR-078 - Shopping list

The application shall provide a shopping list based
on the generated recipe.

When ingredient availability information has been
provided, users shall be able to identify missing
ingredients and quantities.

Users shall be able to copy the shopping list.

#### FR-079 - Equipment list

Detailed recipes shall provide a list of required
cooking equipment and utensils.

The recipe shall respect declared equipment limitations.

#### FR-080 - Preparation organization

The application shall provide preliminary preparation
instructions when applicable.

These instructions may include ingredient cleaning,
cutting, measuring, soaking, thawing and equipment
preparation.

#### FR-081 - Chronological instructions

Recipe instructions shall be organized into clear
and logically ordered preparation steps.

Dependencies and parallel activities shall be
identified when relevant.

#### FR-082 - Cooking parameters

Recipe instructions shall specify relevant cooking
parameters, including:

- Cooking duration.
- Temperature.
- Heat intensity.
- Cooking method.
- Visual or textural indicators.

Instructions shall be adapted to the selected
cooking equipment and difficulty level.

#### FR-083 - Step completion tracking

Users shall be able to mark individual recipe
steps as completed.

The application shall display preparation progress.

Progress tracking shall not require additional
AI generation.

#### FR-084 - Guided cooking mode

The application may provide a dedicated guided
cooking mode.

This mode shall support step-by-step navigation
and controls adapted to mobile cooking environments.

#### FR-085 - Cooking timers

The application may provide timers associated
with individual recipe steps.

Timer interactions shall not require additional
AI generation.

Timer limitations shall be communicated when
reliable background execution is unavailable.

#### FR-086 - Culinary advice

Detailed recipes may include culinary advice,
technique explanations and troubleshooting guidance.

Advice shall be appropriate for the user's
selected cooking difficulty level.

#### FR-087 - Ingredient substitutions

The application shall support compatible ingredient
substitutions when requested or relevant.

Substitutions shall be validated against all
mandatory dietary and food safety constraints.

Affected quantities, cooking instructions and
allergen information shall be updated accordingly.

#### FR-088 - Storage and reheating

Detailed recipes shall provide appropriate storage
and reheating instructions when applicable.

Food safety recommendations shall follow reliable
food safety guidance.

Unverifiable safety recommendations shall not be
presented as established facts.

#### FR-089 - Nutritional information

The application may provide estimated nutritional
information for generated recipes.

Estimated nutritional values shall be clearly
distinguished from verified nutritional data.

The application shall not present estimated values
as medically validated information.

#### FR-090 - Detailed recipe validation

Detailed recipes shall undergo independent validation
against all applicable mandatory constraints.

Validation shall include ingredients, substitutions,
allergens, equipment and cooking requirements.

Unresolved safety conflicts shall prevent the recipe
from being presented as compatible.

#### FR-091 - Recipe state preservation

The application shall preserve the current recipe,
ingredient checklist and preparation progress
during the current session.

Users shall be able to navigate between recipe
sections without losing their current progress.

#### FR-092 - Recipe export

The application shall allow users to copy and print
generated recipes.

Exported recipes shall retain ingredient quantities,
preparation instructions and relevant food safety
information.

#### FR-093 - Recipe customization

Users shall be able to request modifications
to a generated recipe.

Mandatory constraints shall remain active during
customization.

Modified recipes shall undergo renewed validation.

#### FR-094 - Recipe generation feedback

The application shall provide clear feedback during
detailed recipe generation and validation.

Users shall be informed of generation failures
and unresolved validation conflicts.

Previously generated valid recipe content shall
not be silently discarded following a failed request.

### 6.8 User preferences and data persistence

Gustaveo shall provide appropriate data persistence
mechanisms while respecting user privacy and maintaining
a low-friction user experience.

The application shall distinguish between temporary
session data, locally persisted preferences and
potential future account-associated data.

#### FR-095 - Account-free access

Users shall be able to access the core application
features without creating a Gustaveo account.

Recipe suggestion and detailed recipe generation
shall remain available to guest users who have
access to a compatible AI service.

External AI providers may require their own
authentication, credentials or billing arrangements.

Access to application-managed commercial AI services
may require a Gustaveo account and an eligible
active subscription.


#### FR-096 - Session data management

The application shall preserve relevant application
state during the current session, including:

- Recipe configuration.
- Generated recipe suggestions.
- Selected recipes.
- Ingredient checklist state.
- Recipe preparation progress.

#### FR-097 - Local preference persistence

The application shall support local persistence
of non-sensitive user preferences.

Users shall be able to retain supported preferences
between application sessions.

#### FR-098 - Default cooking preferences

Users shall be able to configure default values
for commonly used cooking preferences.

Default preferences may include:

- Number of servings.
- Cooking difficulty.
- Available cooking equipment.

Default values shall remain editable during
individual recipe configuration.

#### FR-099 - Appearance preferences

The application shall support configurable
appearance preferences.

Supported themes may include:

- Light theme.
- Dark theme.
- System theme.

Appearance preferences shall remain independent
of recipe generation logic.

#### FR-100 - Preference management

Users shall be able to review, modify and reset
their locally persisted preferences.

Changes shall be reflected consistently throughout
the application.

#### FR-101 - Sensitive data handling

Food allergy and intolerance information shall
not be persistently stored by default.

The MVP shall not provide persistent storage
of declared food allergies and intolerances.

Sensitive information shall not be unnecessarily
included in application logs or analytics.

#### FR-102 - Local data deletion

Users shall be able to delete application-managed
data stored locally on their device.

Destructive actions shall require clear user
confirmation.

The scope of local data deletion shall be
communicated to the user.

#### FR-103 - Data minimization

The application shall collect and process only
the information necessary to provide its
supported functionality.

Unnecessary personal information shall not
be included in AI generation requests.

#### FR-104 - Data processing transparency

Users shall be informed about the processing,
storage and transmission of their data.

The application shall disclose the involvement
of external AI service providers when applicable.

#### FR-105 - Storage abstraction

Data persistence mechanisms shall be designed
independently of the core application logic.

The application architecture shall allow additional
storage mechanisms to be introduced without
requiring a complete redesign.

#### FR-106 - Future user account support

The application architecture shall allow the
future introduction of optional user accounts.

Account-related features may include:

- Cross-device synchronization.
- Persistent recipe favorites.
- Permanent recipe history.
- Personalized cooking profiles.
- Saved ingredient inventories.

The introduction of user accounts shall not
remove access to core guest functionality.

#### FR-107 - Storage failure handling

The application shall handle unavailable,
restricted or failed local storage gracefully.

Core application functionality shall remain
accessible when persistent storage is unavailable.

Users shall be informed when preferences
cannot be saved.

#### FR-108 - Preference persistence control

Users shall be able to control the persistence
of optional cooking preferences.

Disabling optional preference persistence shall
not prevent recipe generation.

Previously stored optional preferences shall
be removable by the user.

### 6.9 Cross-platform availability

Gustaveo shall be designed as a mobile-first,
cross-platform application.

The application architecture shall support future
distribution across web and mobile platforms while
maximizing shared application logic.

#### FR-109 - Web application availability

Gustaveo shall be accessible through modern web
browsers on desktop, tablet and mobile devices.

#### FR-110 - Installable web application

The application shall support future deployment
as a Progressive Web Application (PWA).

Users shall be able to install the application
on compatible devices.

#### FR-111 - Android application support

The application architecture shall support future
packaging and distribution as an Android application
through the Google Play Store.

#### FR-112 - iOS application support

The application architecture should allow future
packaging and distribution as an iOS application
without requiring a complete application redesign.

#### FR-113 - Cross-platform feature consistency

Core application functionality shall remain
consistent across supported platforms.

Platform-specific limitations shall be handled
gracefully and communicated when necessary.

#### FR-114 - Native device integration

The application architecture shall allow future
integration with native device capabilities,
including:

- Camera access.
- Local notifications.
- Cooking timers.
- Screen wake lock.
- File storage.
- Barcode scanning.
- Voice interaction.

Native integrations shall remain optional
when not supported by the current platform.

#### FR-115 - Offline availability

The application architecture shall support future
offline access to previously stored recipes
and compatible local functionality.

AI-powered generation shall require a network
connection when using a remote AI service.

#### FR-116 - Shared backend services

Supported application platforms shall rely on
shared backend services wherever appropriate.

Security, recipe generation and constraint
validation shall remain consistent across
supported platforms.

## 7. User journey

Gustaveo shall provide an intuitive and consistent
user journey across supported platforms.

The application shall minimize unnecessary interactions
while allowing users to progressively refine their
culinary preferences and constraints.

### 7.1 User experience principles

The user experience shall be based on the following
principles:

- Mobile-first design.
- Account-free access to core functionality.
- Progressive disclosure of advanced options.
- Clear and consistent navigation.
- Preservation of application state.
- Accessible food safety configuration.
- Minimal unnecessary AI generation requests.
- Clear feedback during application operations.

Optional configuration shall not create unnecessary
barriers to recipe discovery.

### 7.2 Primary user journey

The primary user journey shall consist of the
following stages:

1. Access the application.
2. Start a recipe discovery session.
3. Configure culinary preferences and constraints.
4. Validate the selected configuration.
5. Generate personalized recipe suggestions.
6. Review and compare available suggestions.
7. Select a recipe suggestion.
8. Generate and validate the detailed recipe.
9. Review ingredients and required equipment.
10. Prepare the recipe using the provided instructions.

Users shall be able to navigate between relevant
stages without unnecessarily losing their selections
or previously generated content.

### 7.3 Quick discovery journey

Users shall be able to generate recipe suggestions
using reasonable default configuration values.

Advanced preferences shall remain optional.

Food safety configuration shall remain clearly
accessible throughout the configuration process.

The absence of declared allergies shall not be
interpreted as a guarantee of allergen safety.

### 7.4 Advanced configuration journey

Users shall be able to progressively access
additional configuration options, including:

- Dietary patterns.
- Food allergies and intolerances.
- Ingredient preferences and availability.
- Cooking equipment.
- Time and budget preferences.
- Culinary styles and origins.
- Additional cooking instructions.

Advanced configuration shall remain integrated
with the primary recipe discovery journey.

### 7.5 Recipe selection journey

Users shall be able to review, compare and sort
generated recipe suggestions.

Users may select a suggestion, regenerate individual
suggestions, request additional suggestions or return
to the configuration interface.

Previously generated suggestions shall remain
accessible during the current session.

### 7.6 Recipe preparation journey

After selecting a recipe, users shall be able to:

- Review the complete recipe.
- Review ingredient quantities and equipment.
- Identify missing ingredients.
- Access the shopping list.
- Adjust the number of servings.
- Follow preparation instructions.
- Track ingredient and step completion.

Where supported, users may access a dedicated
guided cooking mode.

### 7.7 Alternative and failure journeys

The application shall support alternative user
journeys for situations including:

- Conflicting configuration selections.
- Unsatisfied mandatory constraints.
- Unavailable recipe suggestions.
- AI generation failures.
- Recipe validation failures.
- Network connection failures.
- Unavailable local storage.
- Unsupported platform capabilities.

Users shall receive clear explanations and
appropriate recovery options.

Mandatory constraints shall never be automatically
relaxed to recover from a failed operation.

### 7.8 Screen inventory

| ID | Screen | Purpose |
|----|--------|---------|
| SCR-001 | Home | Application entry point |
| SCR-002 | Recipe configuration | Preference and constraint selection |
| SCR-003 | Recipe suggestions | Recipe discovery and comparison |
| SCR-004 | Detailed recipe | Complete recipe presentation |
| SCR-005 | Shopping list | Ingredient shopping preparation |
| SCR-006 | Cooking mode | Guided recipe preparation |
| SCR-007 | Session history | Previous session results |
| SCR-008 | Settings | Application preferences |
| SCR-009 | About and privacy | Application and privacy information |

The screen inventory represents logical application
views rather than mandatory independent pages.

Screen availability shall depend on the implemented
feature scope and supported platform capabilities.

### 7.9 Navigation and state preservation

The application shall provide consistent navigation
between its supported screens.

Navigation shall preserve relevant configuration,
generated content and preparation progress during
the current session.

Previously generated recipes shall remain associated
with the configuration used to generate them.

Recipes shall not be presented as compatible with
modified mandatory constraints without renewed
validation.

Destructive navigation actions shall be clearly
communicated when they may result in data loss.

### 7.10 Cross-platform user experience

The user journey shall remain consistent across
web and supported mobile platforms.

Navigation patterns and interaction controls may
adapt to platform conventions and screen dimensions.

Platform-specific features shall enhance the user
experience without becoming mandatory dependencies
of the core application.

## 8. Recipe generation

Gustaveo shall use artificial intelligence to generate
personalized culinary content from structured user
preferences and constraints.

AI-generated content shall be processed, validated
and presented through controlled application workflows.

### 8.1 Generation workflow

Recipe generation shall follow a two-stage process:

1. Generation of concise recipe suggestions.
2. Generation of a detailed recipe from a selected
   suggestion.

Both stages shall preserve all applicable mandatory
constraints.

Generated content shall undergo validation before
being presented as compatible with user requirements.

### 8.2 Structured generation requests

Generation requests shall be constructed from
structured application data.

Requests shall distinguish between:

- Generation operation.
- Output language.
- Mandatory food safety constraints.
- Mandatory dietary constraints.
- Ingredient requirements and exclusions.
- Ingredient availability.
- Cooking equipment limitations.
- Time constraints.
- Flexible culinary preferences.
- Additional user instructions.

Internal identifiers shall remain independent
of the selected application language.

Only information necessary for the requested
operation shall be transmitted.

### 8.3 Generation instruction management

AI generation instructions shall be maintained
independently of the user interface.

Generation instructions and associated output
schemas shall be versioned.

The application shall distinguish between
system-controlled instructions and user-provided
content.

User-provided instructions shall not override
mandatory application rules or safety constraints.

### 8.4 Structured generation responses

AI-generated responses shall conform to predefined
structured data schemas.

Separate response schemas shall be defined for:

- Recipe suggestions.
- Detailed recipes.
- Recipe modifications.
- Ingredient substitutions.

Structured responses shall support automated
validation, localization and application rendering.

Malformed or incomplete responses shall not be
presented as successfully validated content.

### 8.5 Generation validation

Generated content shall undergo multiple
validation stages, including:

- Structural validation.
- Mandatory constraint validation.
- Food safety and allergen validation.
- Culinary consistency checks.

Validation shall consider both ingredient lists
and preparation instructions.

Mandatory constraint validation shall not rely
exclusively on the generating AI model.

Unknown or unverifiable compatibility shall be
distinguished from verified incompatibility.

Automated validation shall not be presented as
a guarantee of food safety or culinary success.

### 8.6 Generation failure management

The application shall handle generation failures,
including:

- Invalid or incomplete responses.
- Unsatisfied mandatory constraints.
- Unresolved validation conflicts.
- Provider errors.
- Network failures.
- Request timeouts.
- Service unavailability.
- Usage limit exhaustion.

Automatic retries shall be limited and performed
only when appropriate.

Mandatory constraints shall never be relaxed
automatically during error recovery.

Previously validated results shall be preserved
when possible.

### 8.7 Partial generation results

When only part of a generated suggestion set
passes validation, the application may present
the valid subset.

Users shall be informed when the requested
number of suggestions cannot be provided.

Invalid suggestions shall not be presented
as compatible results.

### 8.8 Generation efficiency

The application shall minimize unnecessary
AI generation requests.

Operations that do not require AI processing
shall be performed without additional generation.

Such operations may include:

- Sorting existing suggestions.
- Navigating between screens.
- Updating ingredient checklists.
- Tracking preparation progress.
- Copying or printing existing recipes.

Previously generated content may be reused
when its associated configuration and validation
state remain applicable.

### 8.9 Usage and cost management

The application shall provide mechanisms to
control AI service consumption and operating costs.

These mechanisms shall include:

- Configurable request limits.
- Request and response size limits.
- Limited automatic retries.
- Duplicate request prevention.
- Usage monitoring.
- Abuse prevention.
- Configurable operational budget limits.

Usage restrictions shall be communicated clearly
to affected users.

Usage controls shall be enforced by trusted
backend services rather than exclusively by
client applications.

### 8.10 AI provider independence

The application architecture shall minimize
unnecessary dependencies on a specific AI
service provider.

Provider-specific request handling and response
processing shall remain separated from core
application functionality.

The architecture should allow AI providers
and models to be replaced or extended without
requiring a complete application redesign.

### 8.11 Generation traceability

The application shall support appropriate
technical traceability of generation operations.

Technical metadata may include:

- Request identifier.
- Generation operation.
- Model identifier.
- Instruction version.
- Response schema version.
- Processing duration.
- Usage metrics.
- Validation outcome.
- Error category.

Traceability mechanisms shall respect data
minimization and privacy requirements.

Sensitive user information shall not be
unnecessarily retained.

### 8.12 AI service security

Application-managed AI credentials shall remain
protected within trusted backend environments.

Application-managed credentials shall not be
exposed through:

- Public source code repositories.
- Client-side application code.
- Mobile application packages.
- Public configuration files.
- User-facing error messages.

User-managed credentials and authorization tokens
shall be handled securely according to the
supported access mechanism and applicable
provider security requirements.

Credentials shall never be included in AI prompts
or application logs.

Generation requests and responses shall be
treated as untrusted data.

The application shall prevent user-provided
content from overriding internal security rules
or accessing protected application resources.

### 8.13 AI-generated content transparency

Users shall be informed that culinary suggestions
and recipes are generated using artificial
intelligence.

Estimated, uncertain and unverifiable information
shall be clearly distinguished from independently
validated information.

AI-generated content shall not be presented
as professionally tested recipes unless such
testing has actually been performed.

### 8.14 AI provider selection and user-managed access

Gustaveo shall be designed to support multiple
AI service access mechanisms.

Supported access mechanisms may include:

- Application-managed AI services.
- User-authorized AI account connections.
- User-provided API credentials (BYOK).
- Compatible local or self-hosted AI services.

Users should be able to select their preferred
AI provider when multiple providers are supported.

Account-based integrations shall rely exclusively
on officially supported authentication and
authorization mechanisms.

User-managed API credentials shall be handled
securely and in accordance with provider
requirements.

The application shall clearly communicate:

- The selected AI provider.
- The active access mechanism.
- Applicable usage limitations.
- Billing responsibilities.
- Provider-specific capabilities and limitations.

The application shall not automatically switch
to a different billing mechanism without explicit
user authorization.

All supported AI providers shall remain subject
to the same mandatory validation, food safety
and application security requirements.

Provider-specific integrations shall remain
independent of the core culinary application logic.


### 8.15 Service access and monetization

Gustaveo shall adopt a freemium service model
while remaining an open-source application.

#### 8.15.1 Free access

The free application shall provide access to
core culinary functionality.

Users shall be able to generate recipes using
compatible personal AI accounts, user-managed
API credentials or supported self-hosted AI
services.

The availability of free AI generation shall
depend on the selected provider and its
applicable usage conditions.

The free application may display advertisements.

#### 8.15.2 Subscription-based access

Gustaveo shall support multiple paid subscription
tiers providing access to an application-managed
AI generation service, referred to as Gustaveo AI.

Access to Gustaveo AI shall require an eligible
active subscription.

Subscription tiers may differ according to:

- Included generation credits or quotas.
- Available AI models.
- Supported AI generation operations.
- Generation priority.
- Additional service capabilities.
- Advertising preferences.

Subscription pricing, usage limitations and
billing conditions shall be clearly communicated
to users.

#### 8.15.3 Subscription plan extensibility

Subscription plans shall be configurable
independently of the core application logic.

The application architecture shall support
the introduction, modification and retirement
of subscription plans without requiring a
complete application redesign.

Plan definitions shall support localization,
regional pricing and different billing periods.

Existing subscription commitments shall be
handled according to applicable service terms.

#### 8.15.4 Generation credit management

The application may implement a credit-based
system for application-managed AI generation.

Credit consumption may vary according to:

- Generation operation.
- Selected AI model.
- Processing requirements.
- Generated content type.
- Associated service costs.

Users shall be informed of their available
credit balance and applicable consumption rules.

Credit allocation, consumption, expiration
and renewal rules shall be clearly defined.

The architecture may support future purchases
of additional generation credits.

#### 8.15.5 Subscription lifecycle management

The application architecture shall support
subscription lifecycle operations, including:

- Subscription activation.
- Subscription renewal.
- Subscription upgrades.
- Subscription downgrades.
- Subscription cancellation.
- Subscription expiration.
- Payment failure handling.
- Purchase restoration where applicable.

Subscription changes shall not unnecessarily
remove access to previously generated content.

#### 8.15.6 Advertising principles

Advertisements shall not interfere with
essential culinary functionality.

Advertisements shall not obscure ingredient
information, cooking instructions or
food safety warnings.

Advertisements shall not interrupt active
recipe preparation workflows.

Sensitive dietary and food allergy information
shall not be used for advertising targeting.

Advertising behavior shall respect applicable
privacy and consent requirements.

#### 8.15.7 Billing and access control

Subscription eligibility, generation credits
and usage quotas shall be enforced by trusted
backend services.

The application shall not initiate paid
AI generation without appropriate
user authorization.

The application shall prevent unauthorized
access to subscription-restricted services.

Platform-specific billing requirements
shall be respected.

#### 8.15.8 Feature accessibility

Essential culinary functionality, accessibility
features and food safety mechanisms shall
remain independent of subscription tiers.

Subscription restrictions shall primarily
apply to application-managed resources
and additional service capabilities.

Mandatory validation and security mechanisms
shall remain active regardless of the user's
subscription status.

#### 8.15.9 Open-source compatibility

Commercial operation of Gustaveo services
shall remain compatible with the project's
open-source licensing model.

Access to application-managed infrastructure
and AI services may be subject to separate
service terms and usage conditions.

## 9. Non-functional requirements

Gustaveo shall satisfy appropriate quality,
security, performance and maintainability
requirements throughout its development
and operational lifecycle.

### 9.1 Performance

#### NFR-001 - Application responsiveness

The application shall provide responsive
interactions across supported devices.

Operations that do not require external
services shall minimize unnecessary latency.

#### NFR-002 - Web performance

The application should target the following
Core Web Vitals thresholds:

- Largest Contentful Paint (LCP): 2.5 seconds
  or less.
- Interaction to Next Paint (INP): 200
  milliseconds or less.
- Cumulative Layout Shift (CLS): 0.1 or less.

These indicators shall be evaluated at the
75th percentile under representative usage
conditions.

#### NFR-003 - Operation feedback

The application should provide initial visual
feedback within 300 milliseconds following
the initiation of a potentially long-running
operation.

#### NFR-004 - External service latency

AI generation latency shall be monitored
separately from application performance.

External service latency shall not unnecessarily
block unrelated application interactions.

#### NFR-005 - Resource optimization

Application assets, network requests and
processing operations shall be optimized
to minimize unnecessary resource consumption.

### 9.2 Accessibility

#### NFR-006 - Accessibility standard

Gustaveo shall target conformance with
WCAG 2.2 Level AA for its web interface.

Equivalent accessibility principles shall
be applied to supported native platforms.

#### NFR-007 - Keyboard accessibility

Essential functionality shall be accessible
through keyboard navigation.

Interactive elements shall provide visible
focus indicators.

#### NFR-008 - Assistive technology support

The application shall use appropriate semantic
structures, accessible names and meaningful
relationships between interface elements.

Essential functionality shall remain accessible
through supported assistive technologies.

#### NFR-009 - Visual accessibility

The application shall provide sufficient
contrast, readable typography and appropriate
visual hierarchy.

Information shall not be communicated
exclusively through color.

#### NFR-010 - Accessible interactions

Interactive controls shall provide appropriate
target sizes and accessible interaction methods.

The application shall respect supported user
preferences concerning text scaling and
reduced motion.

#### NFR-011 - Accessible food safety information

Food safety warnings, allergen information
and mandatory constraint conflicts shall
remain accessible regardless of device,
theme or interaction method.

### 9.3 Responsive design and usability

#### NFR-012 - Mobile-first design

The application shall follow a mobile-first
design approach.

Interfaces shall progressively adapt to
larger screen dimensions.

#### NFR-013 - Responsive layout

Essential functionality shall remain usable
at viewport widths of 320 CSS pixels and
above.

Unnecessary horizontal scrolling shall
be avoided.

#### NFR-014 - Interface consistency

The application shall maintain consistent
interaction patterns, visual components
and terminology.

#### NFR-015 - Cooking environment usability

Recipe preparation interfaces shall account
for practical mobile cooking environments.

Essential instructions shall remain readable
and accessible with minimal interaction.

#### NFR-016 - Non-intrusive monetization

Advertising and subscription-related interfaces
shall not obstruct essential culinary
functionality or food safety information.

### 9.4 Security

#### NFR-017 - Security by design

Security requirements shall be considered
throughout the application design,
development and deployment processes.

#### NFR-018 - Secure communications

Remote application communications shall
use appropriately secured transport
protocols.

Sensitive information shall not be
transmitted through insecure channels.

#### NFR-019 - Credential protection

Application-managed credentials shall
remain within trusted environments.

User-managed credentials shall be handled
according to their access mechanism and
applicable provider security requirements.

Credentials shall not be exposed through
public repositories, logs or unauthorized
application interfaces.

#### NFR-020 - Input and output validation

External inputs and generated outputs
shall be treated as untrusted data.

Appropriate validation and sanitization
mechanisms shall be implemented.

#### NFR-021 - Authentication and authorization

Where authentication is required, the
application shall use appropriate secure
authentication mechanisms.

Access to protected resources shall be
subject to authorization checks.

#### NFR-022 - Subscription security

Subscription eligibility, payment status,
generation credits and protected service
access shall be verified by trusted
backend services.

#### NFR-023 - Abuse prevention

Public services shall implement appropriate
protection against unauthorized usage,
automated abuse and resource exhaustion.

#### NFR-024 - Dependency security

Application dependencies shall be monitored
for known security vulnerabilities.

Security updates shall be evaluated and
applied according to their severity and
operational impact.

#### NFR-025 - Secret detection

Source code repositories and continuous
integration workflows shall incorporate
appropriate secret detection mechanisms.

#### NFR-026 - Security reference standards

Application security practices shall be
guided by relevant OWASP recommendations
and other applicable security standards.

### 9.5 Privacy and data protection

#### NFR-027 - Privacy by design and by default

Privacy requirements shall be considered
throughout the application lifecycle.

Default configurations shall minimize
unnecessary personal data processing.

#### NFR-028 - Regulatory compliance

The application shall comply with applicable
data protection and privacy regulations,
including the General Data Protection
Regulation (GDPR) where applicable.

#### NFR-029 - Data minimization

Personal data collection, transmission
and retention shall be limited to what
is necessary for supported functionality.

#### NFR-030 - Sensitive information protection

Food allergy and intolerance information
shall receive appropriate protection.

Sensitive information shall not be used
for advertising targeting.

#### NFR-031 - Third-party data processing

The involvement of external AI providers,
advertising services, analytics services
and payment processors shall be documented.

Applicable data processing responsibilities
and requirements shall be assessed before
production deployment.

#### NFR-032 - User privacy controls

The application shall provide appropriate
mechanisms for users to exercise applicable
privacy rights and manage their data.

#### NFR-033 - Data retention

Data retention periods shall be defined
according to operational necessity and
applicable legal requirements.

#### NFR-034 - Consent management

Where consent is legally required, the
application shall provide appropriate
consent collection, management and
withdrawal mechanisms.

### 9.6 Reliability and resilience

#### NFR-035 - Graceful degradation

The application shall handle unavailable
services and unsupported capabilities
without unnecessarily disabling unrelated
functionality.

#### NFR-036 - Failure isolation

Failures affecting external providers
shall not unnecessarily propagate to
independent application components.

#### NFR-037 - Timeout and retry management

External service operations shall use
appropriate timeout and retry policies.

Automatic retries shall be bounded and
shall not cause uncontrolled resource
consumption.

#### NFR-038 - Data integrity

Application state and persisted data
shall remain consistent during supported
operations.

#### NFR-039 - Transaction integrity

Subscription and credit management
operations shall prevent duplicate
charges and inconsistent credit balances.

Repeated processing of the same billing
event shall not create unintended effects.

#### NFR-040 - Recovery mechanisms

Appropriate recovery mechanisms shall
be defined for operational failures
and data loss scenarios.

#### NFR-041 - Food safety failure handling

When mandatory food safety validation
cannot be completed, the application
shall not present affected recipes
as compatible.

### 9.7 Maintainability

#### NFR-042 - Code readability

Source code shall prioritize readability,
consistency and explicit responsibilities.

Unnecessary complexity shall be avoided.

#### NFR-043 - Coding standards

The project shall maintain documented
coding conventions and formatting rules.

#### NFR-044 - Technical documentation

Relevant architecture, configuration,
development and deployment procedures
shall be documented.

#### NFR-045 - Architectural decision records

Significant architectural decisions
shall be documented through appropriate
Architectural Decision Records (ADRs).

#### NFR-046 - Dependency management

External dependencies shall be introduced
according to documented technical needs.

Unnecessary dependencies shall be avoided.

#### NFR-047 - Version management

Application releases shall follow a
documented versioning strategy.

Significant changes shall be recorded
in the project changelog.

### 9.8 Modularity and extensibility

#### NFR-048 - Separation of concerns

Presentation, application logic, domain
rules and infrastructure responsibilities
shall remain appropriately separated.

#### NFR-049 - Provider abstraction

External AI provider integrations shall
remain independent of core culinary
application logic.

#### NFR-050 - Infrastructure abstraction

Storage, authentication, payment,
advertising and monitoring integrations
shall remain appropriately isolated
from core domain functionality.

#### NFR-051 - Configuration-driven behavior

Extensible application behavior shall
be configuration-driven where appropriate.

This may include:

- Dietary patterns.
- Ingredient catalogs.
- Supported languages.
- AI provider configurations.
- Subscription plans.
- Generation limits.
- Advertising behavior.

#### NFR-052 - Feature extensibility

New functionality shall be introducible
without requiring unnecessary modifications
to unrelated application components.

#### NFR-053 - Backward compatibility

Changes to supported data formats and
interfaces shall consider compatibility
with existing application data and clients.

Appropriate migration mechanisms shall
be provided when necessary.

### 9.9 Scalability

#### NFR-054 - Workload scalability

The application architecture shall support
future growth in user activity and
generation workloads.

#### NFR-055 - Resource consumption limits

Application-managed resources shall
be subject to appropriate operational
limits.

#### NFR-056 - Concurrent operation management

Concurrent requests shall be handled
without compromising data integrity,
security or subscription usage controls.

#### NFR-057 - Cost scalability

Infrastructure and AI service consumption
shall be measurable and controllable.

Growth in user activity shall not result
in uncontrolled operating expenses.

### 9.10 Platform compatibility

#### NFR-058 - Browser compatibility

The web application shall support a
documented range of modern browsers.

#### NFR-059 - Device compatibility

Essential functionality shall remain
consistent across supported desktop,
tablet and mobile devices.

#### NFR-060 - Progressive enhancement

Optional platform capabilities shall
enhance the application without becoming
mandatory dependencies of core functionality.

#### NFR-061 - Distribution compatibility

The architecture shall account for
applicable requirements associated with
future web and mobile application
distribution channels.

### 9.11 Testability and quality assurance

#### NFR-062 - Automated testing

The project shall support automated
testing of relevant application components
and workflows.

#### NFR-063 - Domain rule testing

Mandatory culinary, dietary and food
safety validation rules shall be
independently testable.

#### NFR-064 - External service testing

External service integrations shall
support controlled testing without
requiring unnecessary live API consumption.

#### NFR-065 - Regression testing

Critical application workflows shall
be covered by appropriate regression
tests.

#### NFR-066 - Continuous integration

The project shall support automated
quality checks through continuous
integration workflows.

#### NFR-067 - Accessibility testing

Accessibility requirements shall be
evaluated through appropriate automated
and manual testing.

#### NFR-068 - AI generation evaluation

AI generation quality shall be evaluated
using representative culinary scenarios,
mandatory constraint combinations and
invalid response cases.

Evaluation shall account for the
non-deterministic nature of AI-generated
content.

### 9.12 Observability

#### NFR-069 - Operational logging

The application shall provide appropriate
technical logging for troubleshooting
and operational monitoring.

#### NFR-070 - Sensitive data exclusion

Logs and monitoring systems shall never retain
API credentials, authentication tokens or
other protected secrets.

During the MVP, logs and monitoring systems
shall not persist declared food allergies
or intolerances.

Other personal information shall only be
retained when necessary and in accordance
with applicable privacy requirements.

#### NFR-071 - Error monitoring

Application failures shall be identifiable
through appropriate error reporting
and monitoring mechanisms.

#### NFR-072 - Usage monitoring

Application-managed AI consumption,
generation failures and operating costs
shall be measurable.

#### NFR-073 - Operational health monitoring

Production services shall provide
appropriate mechanisms for monitoring
availability and operational health.

### 9.13 Resource efficiency

#### NFR-074 - Efficient AI consumption

AI generation shall be used only when
it provides meaningful application value.

#### NFR-075 - Efficient data transfer

The application shall minimize unnecessary
network transfers and redundant requests.

#### NFR-076 - Efficient client processing

Client-side processing shall avoid
unnecessary computational workloads
and excessive battery consumption.

#### NFR-077 - Sustainable resource usage

Infrastructure and AI model selection
should consider resource efficiency
alongside quality, performance and cost.

## 10. MVP scope

The Minimum Viable Product (MVP) of Gustaveo
shall provide a complete and usable personalized
recipe discovery and generation experience.

The MVP shall prioritize core culinary value,
food safety, accessibility and technical
reliability while limiting unnecessary
implementation complexity.

### 10.1 MVP objectives

The MVP shall allow users to:

- Access the application without creating
  a Gustaveo account.
- Configure culinary preferences and constraints.
- Declare food allergies and intolerances.
- Select available ingredients and equipment.
- Generate personalized recipe suggestions.
- Review and select a recipe suggestion.
- Generate a complete and validated recipe.
- Follow the provided preparation instructions.

The MVP shall demonstrate the feasibility
of the complete recipe generation workflow.

### 10.2 Prioritization methodology

MVP functionality shall be prioritized using
the MoSCoW methodology:

- Must have: essential MVP requirements.
- Should have: important but non-blocking
  requirements.
- Could have: optional requirements subject
  to available development resources.
- Won't have this time: requirements deferred
  to subsequent releases.

Deferred functionality shall remain part
of the long-term product vision.

### 10.3 Must-have functionality

The MVP shall include the following essential
capabilities:

#### Food safety

- Selection of the 14 regulated allergen
  categories.
- Custom food exclusions.
- Mandatory constraint prioritization.
- Configuration conflict detection.
- Independent allergen and constraint validation.
- Food safety warnings and disclaimers.

#### Recipe configuration

- Primary dietary pattern selection.
- Categorized ingredient catalog.
- Ingredient search and multiple selection.
- Ingredient preference and availability modes.
- Mandatory ingredient exclusions.
- Serving size configuration.
- Cooking time constraints.
- Cooking difficulty preferences.
- Cooking equipment configuration.
- Culinary style preferences.
- Additional user instructions.

#### AI generation

- At least one operational AI provider.
- At least one supported user-managed AI
  access mechanism.
- Structured generation requests.
- Structured generation responses.
- Recipe suggestion generation.
- Detailed recipe generation.
- Independent response validation.
- Generation feedback and error handling.
- Appropriate usage and resource limits.

#### Recipe presentation

- Responsive recipe suggestion components.
- Essential suggestion information.
- Recipe selection.
- Complete ingredient lists.
- Ingredient quantities and measurement units.
- Required cooking equipment.
- Chronological preparation instructions.
- Relevant food safety information.

#### User experience

- Mobile-first web interface.
- Accessible interaction controls.
- English and French language support.
- Local language preference persistence
  when storage is available and permitted.
- Internationalization-ready architecture.
- Account-free access to core functionality.
- Session state preservation.
- Clear navigation and recovery options.
- AI provider configuration.

#### Technical foundations

- Separation of application responsibilities.
- AI provider abstraction.
- Secure credential handling.
- Independent validation mechanisms.
- Privacy-aware data processing.
- Automated testing of critical domain rules.
- Continuous integration quality checks.
- Basic operational monitoring.
- Resource and cost controls.
- Architecture compatible with future
  subscription-based services.

### 10.4 Should-have functionality

The following capabilities should be included
when development resources permit:

- Ingredient quantity availability.
- Culinary origin preferences.
- Meal occasion preferences.
- Recipe suggestion sorting.
- Individual suggestion regeneration.
- Additional suggestion generation.
- Ingredient checklists.
- Preparation progress tracking.
- Shopping list generation.
- Serving size adjustment after generation.
- Validated ingredient substitutions.
- Recipe customization.
- Recipe copying and printing.
- Session recipe history.
- Local persistence of non-sensitive preferences.
- Configurable appearance themes.

The absence of these capabilities shall not
prevent validation of the essential MVP workflow.

### 10.5 Could-have functionality

The following capabilities may be included
when technically feasible and compatible with
the MVP development schedule:

- Advanced nutritional preferences.
- Additional AI provider integrations.
- Additional official AI account-based
  authentication mechanisms beyond the
  selected mandatory MVP access mechanism.
- Dedicated guided cooking mode.
- Integrated cooking timers.
- Locally persisted recipe favorites.
- Progressive Web Application installation.

Optional functionality shall not compromise
mandatory quality or food safety requirements.

### 10.6 Out-of-scope functionality

The following capabilities shall remain outside
the initial MVP implementation scope:

- Gustaveo user account management.
- Cross-device synchronization.
- Permanent cloud-based recipe history.
- Persistent allergy and intolerance profiles.
- Application-managed commercial AI services.
- Paid subscription management.
- Generation credit purchasing.
- Payment processing.
- Advertising integration.
- Native Android and iOS distribution.
- Google Play Store publication.
- Local and self-hosted LLM integrations.
- AI-generated recipe illustrations.
- Advanced nutritional analysis.
- Persistent ingredient inventories.
- Meal planning.
- Barcode scanning.
- Voice interaction.

These capabilities may be introduced through
subsequent application releases.

### 10.7 MVP screen inventory

| Screen ID | Screen | Priority |
|-----------|--------|----------|
| SCR-001 | Home | Must have |
| SCR-002 | Recipe configuration | Must have |
| SCR-003 | Recipe suggestions | Must have |
| SCR-004 | Detailed recipe | Must have |
| SCR-005 | Shopping list | Should have |
| SCR-006 | Cooking mode | Could have |
| SCR-007 | Session history | Should have |
| SCR-008 | Settings | Must have |
| SCR-009 | About and privacy | Must have |

Screen priorities shall not restrict the
implementation of equivalent functionality
within shared application views.

### 10.8 MVP AI access model

The MVP shall support at least one technically
and legally compatible user-managed AI
access mechanism.

The selected mechanism may rely on user-managed
API credentials or officially supported
account-based authorization.

Any applicable external provider charges
and usage limitations shall be communicated
to the user.

The MVP shall not require a paid Gustaveo
subscription.

Development and testing may use dedicated
application-managed AI credentials within
controlled environments.

Commercial application-managed AI generation
shall remain outside the initial MVP scope.

### 10.9 MVP quality requirements

Mandatory security, privacy, accessibility
and food safety requirements shall apply
from the initial MVP release.

MVP scope limitations shall not justify
bypassing mandatory validation or security
mechanisms.

Non-functional requirements associated with
deferred features shall become applicable
when those features are implemented.

Performance and reliability objectives shall
be evaluated under representative MVP
usage conditions.

### 10.10 MVP completion conditions

The MVP shall be considered complete when:

- All applicable Must-have requirements
  have been implemented.
- The complete primary user journey
  is operational.
- Critical food safety validation rules
  have been tested.
- At least one supported AI access
  mechanism is operational.
- Critical generation and validation
  failures are handled appropriately.
- Supported languages are available.
- Essential functionality is accessible
  on supported mobile and desktop browsers.
- No unresolved critical security defects
  are known.
- Required development and deployment
  documentation is available.
- Applicable acceptance criteria have
  been satisfied.

Should-have and Could-have requirements
shall not block MVP completion unless
explicitly promoted to Must-have status.

### 10.11 Scope management

Changes to the MVP scope shall be evaluated
according to their impact on:

- Core user value.
- Food safety.
- Security and privacy.
- Technical complexity.
- Development effort.
- External dependencies.
- Operating costs.
- Release readiness.

Significant scope changes shall be documented.

The MVP shall remain a foundation for future
development rather than a limitation of
the long-term product vision.

## 11. Future enhancements

Gustaveo shall be designed as an extensible
culinary application capable of supporting
additional functionality beyond the initial MVP.

The following enhancements represent potential
long-term development opportunities rather than
mandatory initial release requirements.

### 11.1 Enhanced culinary assistance

Future releases may introduce advanced
interactive cooking assistance, including:

- Guided step-by-step cooking.
- Multiple concurrent cooking timers.
- Background timer notifications.
- Screen wake lock during preparation.
- Hands-free voice interaction.
- Contextual culinary assistance.
- Interactive cooking troubleshooting.
- Advanced ingredient substitutions.
- Improved serving size adjustments.
- Cooking technique explanations.
- AI-generated recipe illustrations.

Interactive assistance shall preserve all
applicable mandatory food safety and dietary
constraints.

### 11.2 Meal planning

The application may provide meal planning
capabilities, including:

- Daily and weekly meal planning.
- Multi-day recipe generation.
- Configurable meal schedules.
- Household meal planning.
- Budget-aware meal suggestions.
- Batch cooking and meal preparation.
- Leftover ingredient reuse.
- Consolidated shopping lists.

Meal planning should account for ingredient
availability, dietary constraints, cooking
equipment and user preferences.

### 11.3 Ingredient inventory management

Future releases may provide persistent
ingredient inventory management.

Supported capabilities may include:

- Ingredient quantity tracking.
- Pantry and refrigerator inventories.
- Ingredient expiration date management.
- Ingredient consumption tracking.
- Inventory-based recipe generation.
- Automatic shopping list suggestions.
- Barcode scanning.
- Product information retrieval.
- Food waste reduction recommendations.

Inventory modifications shall remain
reviewable and editable by the user.

Expiration-related recommendations shall
not be presented as guarantees of food safety.

### 11.4 Visual ingredient recognition

The application may support ingredient
identification through image analysis.

Potential capabilities include:

- Ingredient recognition from photographs.
- Refrigerator and pantry content analysis.
- Product packaging recognition.
- Ingredient list extraction.
- Food label analysis.

Automatically recognized ingredients and
extracted information shall be subject to
user confirmation when appropriate.

Image recognition shall not replace
mandatory allergen validation or product
label verification.

### 11.5 User accounts and synchronization

Future releases may introduce optional
Gustaveo user accounts.

Account-related functionality may include:

- Cross-device preference synchronization.
- Persistent recipe history.
- Recipe favorites.
- Custom recipe collections.
- Personalized cooking profiles.
- Saved ingredient inventories.
- Meal planning synchronization.
- Subscription and credit management.

Core guest functionality shall remain
available independently of Gustaveo accounts,
subject to compatible AI access mechanisms.

### 11.6 Household and multi-profile management

The application may support multiple
culinary profiles within a household.

Individual profiles may contain:

- Dietary patterns.
- Ingredient preferences.
- Cooking preferences.
- Food allergies and intolerances.
- Nutritional preferences.

Recipe generation may account for multiple
selected profiles simultaneously.

The application may suggest individual
recipe adaptations when a common recipe
cannot satisfy all applicable preferences.

Mandatory food safety constraints shall
remain active for every relevant profile.

Persistent storage of sensitive profile
information shall require appropriate
privacy and security safeguards.

### 11.7 Advanced nutritional functionality

Future releases may provide enhanced
nutritional information, including:

- Estimated energy values.
- Macronutrient distribution.
- Micronutrient information.
- Nutritional comparisons.
- Configurable nutritional objectives.
- Nutritional meal planning.

Nutritional calculations should rely on
appropriate reference datasets whenever
available.

Estimated nutritional information shall
remain distinguishable from verified data.

The application shall not present itself
as a substitute for professional medical
or nutritional advice.

### 11.8 AI provider ecosystem

The application may progressively expand
its supported AI ecosystem through:

- Additional commercial AI providers.
- Official AI account integrations.
- User-managed API credentials.
- Local and self-hosted AI services.
- Open-weight language models.
- Configurable AI model selection.
- Multimodal AI capabilities.
- Provider-specific feature detection.
- AI model quality evaluation.

Provider-specific capabilities and
limitations shall be clearly communicated.

All supported providers shall remain
subject to applicable validation,
security and privacy requirements.

### 11.9 Commercial service development

Future commercial releases may introduce
the Gustaveo AI service and associated
monetization mechanisms.

Potential capabilities include:

- Multiple configurable subscription tiers.
- Monthly and annual billing periods.
- Generation credit allocation.
- Additional credit purchases.
- Subscription lifecycle management.
- Usage monitoring.
- Subscription and credit dashboards.
- Advertising-supported free access.
- Advertisement-free subscription options.
- Regional pricing.
- Promotional offers.
- Platform-specific payment integration.

Commercial functionality shall remain
consistent with the service access and
monetization principles defined in
Section 8.15.

Essential culinary functionality and
food safety mechanisms shall remain
independent of subscription tiers.

### 11.10 Mobile and native platform development

Future releases may extend Gustaveo
distribution through:

- Progressive Web Application installation.
- Android application packaging.
- Google Play Store distribution.
- iOS application packaging.
- Apple App Store distribution.
- Native device notifications.
- Camera integration.
- Native file management.
- Background cooking timers.
- Screen wake lock.
- Voice interaction.

Platform-specific integrations shall
maximize shared application logic
where technically appropriate.

### 11.11 Offline functionality

Future releases may provide offline
access to compatible functionality,
including:

- Previously saved recipes.
- Ingredient checklists.
- Preparation instructions.
- Shopping lists.
- Locally stored preferences.
- Cooking timers.
- Preparation progress tracking.

Remote AI generation shall remain
dependent on network availability.

Compatible local AI services may
provide additional offline generation
capabilities.

### 11.12 Internationalization expansion

Additional languages and regional
configurations may be introduced
progressively.

Potential enhancements include:

- Additional interface languages.
- Regional measurement systems.
- Localized ingredient catalogs.
- Regional culinary terminology.
- Regional ingredient availability.
- Localized nutritional references.
- Regional pricing and currencies.
- Region-specific food safety information.

Language expansion shall preserve
the application's accessibility and
food safety requirements.

### 11.13 Recipe sharing and community features

Future releases may provide recipe
sharing and collaborative functionality.

Potential capabilities include:

- Shareable recipe links.
- Recipe collection sharing.
- Recipe export and import.
- User-created recipe collections.
- Collaborative household planning.
- Community recipe contributions.
- Recipe ratings and feedback.

Public or shared user-generated content
shall be subject to appropriate privacy,
security and moderation mechanisms.

Shared recipes shall not automatically
be considered compatible with another
user's dietary or food safety constraints.

### 11.14 External service integrations

The application architecture may support
future integrations with external services,
including:

- Food composition databases.
- Product information databases.
- Grocery shopping services.
- Calendar applications.
- Recipe management services.
- Smart kitchen equipment.
- Home automation systems.

External integrations shall remain optional
and appropriately isolated from core
application functionality.

Applicable licensing, privacy, security
and service usage requirements shall
be evaluated before integration.

### 11.15 Self-hosting and developer ecosystem

Future releases may improve support for
independent Gustaveo deployments.

Potential enhancements include:

- Self-hosted deployment documentation.
- Configurable backend environments.
- Custom AI provider configurations.
- Documented application interfaces.
- Containerized deployment.
- Extensible provider adapters.
- Community-maintained translations.
- Community-maintained ingredient datasets.

Self-hosted deployments shall remain
independent of access to commercial
NSS Labs infrastructure unless explicitly
authorized.

### 11.16 Continuous quality improvement

Future development shall include
continuous evaluation and improvement
of application quality.

Improvement areas may include:

- Recipe generation quality.
- Culinary diversity.
- Ingredient recognition accuracy.
- Allergen reference data coverage.
- Constraint validation reliability.
- Accessibility.
- Application performance.
- AI generation efficiency.
- Infrastructure resource consumption.
- Security and privacy protections.

User feedback and representative
evaluation scenarios should inform
future development priorities.

### 11.17 Enhancement prioritization

Future enhancements shall be evaluated
according to:

- User value.
- Food safety implications.
- Technical feasibility.
- Development complexity.
- Infrastructure requirements.
- External service dependencies.
- Operating costs.
- Privacy and security implications.
- Commercial sustainability.
- Maintenance requirements.

The inclusion of an enhancement in
this section shall not constitute
a release commitment.

Implementation priorities and release
schedules shall be maintained separately
within the project roadmap.

## 12. Acceptance criteria

Acceptance criteria shall provide objective
and verifiable conditions for evaluating
Gustaveo's implementation against its
functional and non-functional requirements.

Acceptance criteria shall support development,
quality assurance and release validation.

### 12.1 Acceptance methodology

Acceptance scenarios shall use the
Given / When / Then structure where
appropriate.

- Given: initial conditions and prerequisites.
- When: an action or event occurs.
- Then: the expected observable outcome.
- And: additional conditions or outcomes.

Acceptance criteria shall be associated
with relevant functional and non-functional
requirements.

Validation may involve automated tests,
manual tests, security assessments,
accessibility audits and AI generation
quality evaluations.

### 12.2 Core application access

#### AC-001 - Guest access

Given a user without a Gustaveo account
and with access to a compatible AI service,

When the user accesses the application,

Then the user shall be able to access
the core recipe generation workflow
without creating a Gustaveo account.

#### AC-002 - Default configuration

Given a new recipe discovery session,

When the user does not specify optional
culinary preferences,

Then the application shall provide
appropriate default configuration values.

And optional preferences shall not
prevent recipe generation.

#### AC-003 - Configuration preservation

Given a partially or fully configured
recipe generation request,

When the user navigates between supported
application views,

Then the current configuration shall
remain available during the session.

### 12.3 Food safety and dietary constraints

#### AC-004 - Allergen selection

Given the recipe configuration interface,

When the user accesses food allergy
configuration,

Then all 14 regulated allergen categories
shall be available for selection.

And additional custom exclusions shall
be supported.

#### AC-005 - Mandatory constraint enforcement

Given a vegan dietary pattern, a declared
soy allergy and unavailable oven equipment,

When recipe suggestions are generated,

Then suggestions presented as compatible
shall contain no identified animal-derived
ingredients, soy-containing ingredients
or instructions requiring an oven.

And the generated content shall undergo
independent constraint validation.

#### AC-006 - Conflicting configuration

Given a declared peanut allergy,

When peanuts are selected as a required
ingredient,

Then the application shall identify
the conflict before generation.

And the conflicting request shall not
be submitted until appropriately resolved.

#### AC-007 - Unknown ingredient composition

Given a declared food allergy,

When a generated recipe contains a compound
ingredient whose relevant composition
cannot be established,

Then the application shall not present
the recipe as compatible with that allergy.

#### AC-008 - Independent allergen validation

Given an AI response containing a known
allergen that contradicts a mandatory
user exclusion,

When the response is processed,

Then independent validation shall identify
the incompatibility.

And the affected recipe shall not be
presented as compatible.

#### AC-009 - Constraint preservation

Given an existing recipe configuration
with mandatory food safety constraints,

When the user regenerates, customizes
or modifies a recipe,

Then all applicable mandatory constraints
shall remain active.

And modified content shall undergo
appropriate renewed validation.

#### AC-010 - Unavailable safety validation

Given a generated recipe requiring
mandatory food safety validation,

When the validation mechanism is
unavailable or fails,

Then the recipe shall not be presented
as compatible.

And the user shall receive an appropriate
explanation.

#### AC-011 - Food safety transparency

Given a generated recipe,

When the recipe is presented to the user,

Then relevant allergen information,
warnings and validation limitations
shall remain accessible.

And the application shall not claim
guaranteed allergen safety.

### 12.4 Ingredient and cooking configuration

#### AC-012 - Ingredient selection

Given the ingredient catalog,

When the user searches for and selects
multiple ingredients,

Then the selected ingredients shall
be reflected in the recipe configuration.

And the user shall be able to modify
or remove individual selections.

#### AC-013 - Strict ingredient availability

Given a strict ingredient availability
configuration,

When recipes are generated,

Then recipes presented as compatible
shall use only ingredients explicitly
permitted by the configuration.

#### AC-014 - Ingredient preference handling

Given required, preferred, avoided
and excluded ingredients,

When the generation request is constructed,

Then mandatory requirements and flexible
preferences shall remain distinguishable.

And excluded ingredients shall not be
treated as optional preferences.

#### AC-015 - Equipment compatibility

Given that an oven is explicitly
unavailable,

When recipes are generated,

Then recipes presented as compatible
shall not require oven-based preparation.

#### AC-016 - Cooking time constraints

Given a mandatory maximum total duration,

When recipe suggestions are generated,

Then their estimated total durations
shall not exceed the configured limit.

And preparation, cooking and applicable
waiting times shall be considered.

#### AC-017 - Serving size configuration

Given a selected number of servings,

When a detailed recipe is generated,

Then the recipe shall specify that
number of servings.

And ingredient quantities shall be
appropriate for the requested serving size.

### 12.5 AI generation and provider integration

#### AC-018 - Structured generation request

Given a valid recipe configuration,

When a generation request is constructed,

Then the request shall contain the
applicable structured configuration,
mandatory constraints and output language.

And unnecessary personal information
shall not be included.

#### AC-019 - Recipe suggestion generation

Given a valid recipe configuration
and an operational AI provider,

When the user requests recipe suggestions,

Then the application shall process
and validate the provider response.

And compatible suggestions shall contain
the required presentation information.

#### AC-020 - Detailed recipe generation

Given a selected recipe suggestion,

When the user requests the detailed recipe,

Then the application shall generate
and validate the complete recipe.

And the original mandatory constraints
shall remain active.

#### AC-021 - Invalid AI response

Given an AI response that does not
conform to the expected data schema,

When the response is processed,

Then the application shall detect
the invalid response.

And the response shall not be presented
as successfully validated content.

#### AC-022 - Partial generation results

Given a request for multiple suggestions,

When only a subset passes validation,

Then the application may present
the validated subset.

And the user shall be informed that
the requested quantity could not
be provided.

#### AC-023 - External service failure

Given an active generation request,

When the AI provider becomes unavailable
or the request exceeds its timeout,

Then the application shall display
an appropriate failure message.

And previously validated content shall
remain available when possible.

#### AC-024 - User-managed AI access

Given a supported user-managed AI
access mechanism,

When the user completes the required
provider configuration or authorization,

Then the application shall be able
to submit compatible generation requests.

And applicable provider limitations
and billing responsibilities shall
be communicated.

#### AC-025 - Provider usage limits

Given an exhausted provider usage quota,

When the user requests additional
AI generation,

Then the application shall communicate
the applicable usage limitation.

And it shall not automatically switch
to another billing mechanism.

#### AC-026 - Duplicate request prevention

Given an active generation operation,

When the user repeatedly activates
the same generation control,

Then unintended duplicate generation
requests shall be prevented.

#### AC-027 - Generation efficiency

Given previously generated recipe content,

When the user performs a local operation
such as navigation or sorting,

Then no additional AI generation request
shall be required.

#### AC-028 - Untrusted generation instructions

Given user-provided instructions attempting
to override mandatory constraints or
application security rules,

When the generation request is processed,

Then the mandatory constraints and
security rules shall remain active.

### 12.6 Recipe presentation and preparation

#### AC-029 - Recipe suggestion presentation

Given a validated recipe suggestion,

When the suggestion is displayed,

Then its essential culinary information
shall be readable and accessible.

And relevant food safety information
shall remain available.

#### AC-030 - Complete recipe presentation

Given a validated detailed recipe,

When the recipe is displayed,

Then the user shall be able to access:

- Recipe title and description.
- Number of servings.
- Ingredient quantities and units.
- Estimated preparation and cooking times.
- Required cooking equipment.
- Chronological preparation instructions.
- Relevant food safety information.

#### AC-031 - Missing ingredient identification

Given declared ingredient availability,

When a generated recipe contains
additional ingredients,

Then the missing ingredients shall
be identifiable when the corresponding
functionality is supported.

#### AC-032 - Ingredient checklist

Given a recipe with an ingredient checklist,

When the user marks an ingredient
as collected or prepared,

Then the checklist state shall update.

And no additional AI request shall
be required.

#### AC-033 - Preparation progress

Given a recipe with progress tracking,

When the user completes a preparation step,

Then the corresponding progress state
shall update.

And completed steps shall remain
identifiable during the session.

#### AC-034 - Recipe modification

Given an existing validated recipe,

When the user requests a supported
ingredient substitution or customization,

Then the affected recipe information
shall be updated consistently.

And all applicable mandatory constraints
shall undergo renewed validation.

#### AC-035 - Recipe export

Given a validated recipe and supported
export functionality,

When the user copies or prints the recipe,

Then essential ingredients, quantities,
preparation instructions and relevant
food safety information shall be retained.

### 12.7 Internationalization and localization

#### AC-036 - Language selection

Given a supported application language,

When the user selects that language,

Then the static user interface shall
be displayed using the corresponding
translation resources.

#### AC-037 - Language switching

Given an active recipe configuration,

When the user changes the interface
language,

Then the existing selections and
application state shall be preserved.

#### AC-038 - Localized recipe generation

Given a selected supported output language,

When a recipe is generated,

Then the resulting culinary content
shall use the requested language.

#### AC-039 - Language-independent validation

Given equivalent recipe configurations
in different supported languages,

When mandatory constraints are evaluated,

Then equivalent validation rules
shall be applied.

#### AC-040 - Safety-critical translations

Given an officially supported language,

When food safety information is displayed,

Then the corresponding allergen names,
warnings and disclaimers shall be
available and understandable.

Missing safety-critical translations
shall prevent release of the affected
language configuration.

### 12.8 Data persistence and privacy

#### AC-041 - Session state preservation

Given an active recipe discovery session,

When the user navigates between
supported views,

Then relevant configuration and generated
content shall remain available.

#### AC-042 - Local preference persistence

Given enabled local preference persistence,

When the user closes and subsequently
reopens the application,

Then supported non-sensitive preferences
shall be restored.

#### AC-043 - Local data deletion

Given locally persisted application data,

When the user confirms a supported
data deletion operation,

Then the application shall remove
the data covered by that operation.

#### AC-044 - Sensitive data persistence

Given declared food allergies or
intolerances during the MVP,

When the current session ends,

Then the application shall not retain
those declarations in persistent
application-managed storage.

#### AC-045 - Unavailable local storage

Given restricted or unavailable
persistent browser storage,

When the user accesses the application,

Then core functionality shall remain
available.

And persistence limitations shall
be communicated when relevant.

#### AC-046 - Privacy transparency

Given an external AI generation service,

When the user configures or uses
the service,

Then relevant data processing information
shall be accessible.

And external provider involvement
shall be disclosed.

### 12.9 Responsive design and accessibility

#### AC-047 - Mobile usability

Given a supported mobile browser
with a viewport width of 320 CSS pixels,

When the user accesses the core
application workflow,

Then essential controls and information
shall remain usable.

And unnecessary horizontal scrolling
shall not be required.

#### AC-048 - Desktop usability

Given a supported desktop browser,

When the user accesses the application,

Then the interface shall adapt
appropriately to the available
screen dimensions.

#### AC-049 - Keyboard navigation

Given a user interacting exclusively
through a keyboard,

When the user navigates through
the essential application workflow,

Then all required interactive controls
shall remain accessible.

And keyboard focus shall be visible.

#### AC-050 - Accessible information

Given an interface displaying mandatory
constraint conflicts or food safety warnings,

When the information is presented,

Then its meaning shall not depend
exclusively on color.

And appropriate accessible names and
semantic relationships shall be provided.

#### AC-051 - Assistive technology compatibility

Given a supported browser and assistive
technology configuration,

When the user accesses essential
application functionality,

Then relevant controls, labels,
instructions and status messages
shall remain accessible.

#### AC-052 - Accessibility evaluation

Given a release candidate,

When the web interface is evaluated
against applicable WCAG 2.2 Level AA
success criteria,

Then identified failures shall be
documented and resolved according
to the release quality requirements.

### 12.10 Performance and reliability

#### AC-053 - Operation feedback

Given a potentially long-running
generation operation,

When the user initiates the operation,

Then the application should provide
initial feedback within the defined
300 millisecond performance objective.

#### AC-054 - Web performance evaluation

Given representative supported devices,
network conditions and usage scenarios,

When application performance is measured,

Then results shall be evaluated against
the defined Core Web Vitals objectives.

Measurement conditions and limitations
shall be documented.

#### AC-055 - Bounded retry behavior

Given a recoverable external service error,

When automatic retry behavior is triggered,

Then the configured retry limits
shall be respected.

And mandatory constraints shall not
be relaxed.

#### AC-056 - Previously generated content

Given previously validated recipe content,

When a subsequent generation request fails,

Then the existing content shall not
be silently discarded.

#### AC-057 - Resource limits

Given configured request or resource limits,

When an operation exceeds those limits,

Then the operation shall be rejected
or appropriately restricted.

And uncontrolled resource consumption
shall be prevented.

### 12.11 Security

#### AC-058 - Credential protection

Given a production application build,

When distributed assets, public configuration
and application logs are inspected,

Then no application-managed AI credentials
or other protected secrets shall
be exposed.

#### AC-059 - Unauthorized service access

Given a request without the required
authorization,

When a protected backend operation
is requested,

Then the operation shall be rejected.

#### AC-060 - Malicious input handling

Given malformed or malicious input,

When the application processes the input,

Then the input shall not result in
unauthorized code execution, protected
resource access or security rule bypass.

#### AC-061 - Secret detection

Given a controlled repository or
continuous integration test scenario
containing a synthetic detectable secret,

When the configured secret detection
mechanism is executed,

Then the potential secret shall be
identified and reported.

#### AC-062 - Sensitive logging protection

Given a generation request containing
credentials or sensitive food safety
information,

When technical logging is performed,

Then credentials shall not be retained
in logs.

And unnecessary sensitive information
shall be excluded.

### 12.12 Commercial service acceptance

The following criteria shall become
applicable when commercial functionality
is implemented.

#### AC-063 - Free service access

Given a user without a paid Gustaveo
subscription,

When the user accesses the application,

Then supported core culinary functionality
shall remain available through compatible
user-managed AI access mechanisms.

#### AC-064 - Gustaveo AI authorization

Given a user without an eligible
active subscription,

When the user requests Gustaveo AI
generation,

Then the protected service request
shall be rejected.

#### AC-065 - Subscription entitlement

Given an eligible active subscription,

When the user requests an authorized
Gustaveo AI operation,

Then the applicable subscription
entitlements and usage limits shall
be evaluated by trusted backend services.

#### AC-066 - Credit consumption

Given an available credit balance
and a supported generation operation,

When the operation is processed,

Then credit consumption shall follow
the applicable documented rules.

And the resulting balance shall
remain consistent.

#### AC-067 - Insufficient credits

Given an insufficient generation
credit balance,

When the user requests a credit-based
generation operation,

Then the operation shall not proceed
without appropriate authorization
and available entitlement.

#### AC-068 - Duplicate billing events

Given a previously processed billing event,

When the same event is received again,

Then no unintended duplicate charge,
credit allocation or subscription
modification shall occur.

#### AC-069 - Subscription expiration

Given an expired subscription,

When the user requests Gustaveo AI,

Then subscription-restricted access
shall no longer be available.

And supported free functionality
shall remain accessible.

#### AC-070 - Advertising restrictions

Given an advertisement-supported
application configuration,

When the user follows recipe preparation
instructions,

Then advertisements shall not interrupt
active preparation or obscure essential
culinary and food safety information.

#### AC-071 - Advertising privacy

Given sensitive dietary or food
allergy information,

When advertising services are used,

Then that information shall not be
used for advertising targeting.

#### AC-072 - Subscription independence

Given users with different subscription
tiers,

When equivalent mandatory food safety
constraints are evaluated,

Then the same applicable validation
and security requirements shall apply.

### 12.13 Quality assurance and traceability

#### AC-073 - Critical domain rule testing

Given the implemented mandatory
food safety and dietary validation rules,

When automated domain tests are executed,

Then supported valid, invalid, conflicting
and unverifiable scenarios shall
produce their expected outcomes.

#### AC-074 - External provider simulation

Given a controlled testing environment,

When representative AI responses and
provider failures are simulated,

Then application behavior shall be
verifiable without unnecessary live
AI service consumption.

#### AC-075 - Continuous integration validation

Given a proposed application change,

When the configured continuous integration
workflow is executed,

Then applicable automated quality
and security checks shall produce
reviewable results.

#### AC-076 - Requirement traceability

Given the implemented release scope,

When acceptance validation is performed,

Then applicable requirements shall
be associated with appropriate
verification methods and results.

#### AC-077 - Primary user journey

Given a supported browser, a valid
recipe configuration and an operational
AI access mechanism,

When the user completes the primary
recipe discovery workflow,

Then the user shall be able to:

- Configure preferences and constraints.
- Generate validated recipe suggestions.
- Select a suggestion.
- Generate a validated detailed recipe.
- Access ingredients and equipment.
- Follow preparation instructions.

The complete journey shall remain
consistent with applicable food safety,
security and privacy requirements.

### 12.14 Acceptance status management

Acceptance criteria shall support
the following evaluation statuses:

- Not evaluated.
- Passed.
- Failed.
- Blocked.
- Not applicable.

Acceptance results shall identify
the evaluated application version,
test environment and relevant evidence.

Failed or blocked criteria shall
include appropriate explanations.

A criterion shall only be marked
as passed when sufficient verification
evidence is available.

### 12.15 Release acceptance

A release shall be considered eligible
for acceptance when:

- Applicable mandatory requirements
  have been implemented.
- Applicable mandatory acceptance
  criteria have passed.
- Critical food safety tests have passed.
- No known unresolved critical security
  defects remain.
- Applicable privacy requirements
  have been addressed.
- Required documentation is available.
- Known limitations are documented.
- Release-specific quality requirements
  have been satisfied.

Criteria associated with deferred
functionality shall be marked as
not applicable for the corresponding
release scope.

Any permitted deviation from a
non-mandatory quality objective
shall be documented and justified.

Mandatory food safety and security
requirements shall not be bypassed
through release exceptions.
