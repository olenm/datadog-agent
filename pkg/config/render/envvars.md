# Available environment variable bindings
{{range . -}}
## {{ .Name }}
{{- if .Description }}
{{ .Description }}
{{- end }}

  {{- range .Options}}
    {{- if not .Undocumented or .NoEnvvar }}
- `{{ .Name }}`: {{ if .EnvvarDesc }}{{ .EnvvarDesc }}{{ else }}{{ .Description }}{{ end }}
    {{- end -}}
  {{- end -}}

{{- end -}}
