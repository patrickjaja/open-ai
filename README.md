# Open AI Spryker package
![qr-code.png](qr-code.png)

# setup
 - configure $config[OpenAiConstants::OPENAI_API_KEY] in your config_local.php (you get it from https://platform.openai.com/account/api-keys)

# Description
- OpenAI Client for spryker
- BO UI to manage prompts
- BO UI to generate prompts for:
    - product descriptions
    - seo title
    - seo keywords
    - seo description
- New OpenAi ErrorRenderer
  - OpenAi5YearsApiDebugErrorRenderer
  - OpenAiApiDebugErrorRenderer

# Screenshots
![1.png](1.png)
![2.png](2.png)
![3.png](3.png)
![4.png](4.png)
![5.png](5.png)
![6.png](6.png)
![7.png](7.png)

# Example usage
- use this snipped to upgrade backoffice inputs to openai inputs (also see `Zed/OpenAi/assets/Zed/js/modules/openai.js:4`)
 ```javascript
 attachOpenAiCompletionApiToToForm('textarea[name*="description"]', function(event, languageContext) {
  let nameInput = $('input[name*="'+languageContext+'][name"]');
  let skuInput = $('input[name*="'+languageContext+'][sku"]');
  return {title: nameInput.value, sku: skuInput.value};
 });
 ```

# HowTos Cli
 - docker/sdk up

# Roadmap
 - Workflow Builder UI (Database Model for this OpenAI contains an event system - that is used to trigger a prompt -> see table vsy_openai_prompt_to_event)
   - Inject a prompt through predefined EventFacade trigger Events i.e. ProductCreated, CustomerCreated, CategoryCreated and map Transfer field to prompt response
