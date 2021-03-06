# OpenAPI Generator - Generate TypeScript models only
## Problem
All TypeScript-generators create full api-clients. But we may want to only generate model classes.

## Solution
We can use the 'typescript-angular' generator. But we then have to remove and move some file.

* This also Maps all `Date`s from the Spec to `string`s (otherwise it would map them to js-Dates, which are DateTimes, not Dates).
* This also prefixes all enums and classes with 'Api'
* This configures the configurator to generate string enums (`MYENUM = "MY_ENUM"` instead of `MYENUM = 0`)

```bash
typescript_models_generate(){
   out="src/app/generated/openapi-models"
   spec="my-spec.yaml"

      echo "- Cleaning up" \
   && rm -rf "${out}" \
   && echo "- Generating model classes :" \
   && openapi-generator generate \
         -g typescript-angular \
         --type-mappings=Date=string \
         --model-name-prefix=Api \
         -p=stringEnums=true,fileNaming=kebab-case \
         -i "${spec}" \
         -o "${out}" \
   && echo "- Removing unused files" \
   && cd "${out}" \
   && rm -rf .openapi-generator api .gitignore .openapi-generator-ignore index.ts tsconfig.json api.module.ts \
             configuration.ts git_push.sh README.md model/models.ts variables.ts encoder.ts \
   && echo "- Moving model files one directory up" \
   && mv model/* . \
   && rmdir model \
   && cd -
}
```

Hint: You may also want to use [a `.openapi-generator-ignore`-File](https://github.com/OpenAPITools/openapi-generator/blob/master/docs/customization.md#ignore-file-format)

[Source](https://github.com/OpenAPITools/openapi-generator/tree/master/modules/openapi-generator-maven-plugin)
