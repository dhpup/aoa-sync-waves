Healthcheck will need to be added in Resource Customizations for App of Apps level sync waves to work. 

Group/Kind=argoproj.io/Application
Healthcheck=
```
{
        hs = {}
        hs.status = "Progressing"
        hs.message = ""
        if obj.status ~= nil then
          if obj.status.health ~= nil then
            hs.status = obj.status.health.status
            if obj.status.health.message ~= nil then
              hs.message = obj.status.health.message
            end
          end
        end
        return hs
}
```