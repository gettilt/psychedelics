<!--[[[cog
import cog
import json
with open('config.json') as file:
  config = json.load(file)
  cog.outl(f"# {config['name'].title()}")
]]]-->
# Psychedelics
<!--//[[[end]]]-->

## Mission

Tilt's mission is to map every theme to a basket of stocks for anyone to invest in. Mappings are AI generated and expert curated.
Expert improvements are accepted if they provide a better representation of a given theme.

## Theme Prompt
<!--[[[cog
import cog
import json
with open('config.json') as file:
  config = json.load(file)
  cog.outl(config['prompt'])
]]]-->
Psychedelics are the new way to treat mental illness. Companies experimenting with and producing Psychedelics are poised to win in the fight against mental illness.
<!--[[[end]]]-->

## Theme Stocks

<!--[[[cog
import cog
import csv
import json

with open('context.json') as file:
  contexts = json.load(file)

def _get_context_str_for_ticker(ticker):
  try:
    context = contexts[ticker]
    context_str = context['chat_gpt'] or context['claude'] or ""
  except KeyError:
    context_str = ""

  return context_str

cog.outl("| Ticker  | Context | Source |")
cog.outl("| ------- | ---- | ---- |")

with open('theme.csv') as file:
  reader = csv.reader(file)
  next(reader) # skip the header
  for row in reader:
    context_str = _get_context_str_for_ticker(row[0])
    cog.outl(f"| {row[0]} | {context_str} | {row[1]} |")
]]]-->
| Ticker  | Context | Source |
| ------- | ---- | ---- |
| ABT | Abbott Laboratories, with its diagnostics and neurological drug development, could see indirect benefits from advancements in psychedelic therapies. | chat_gpt |
| ATAI | ATAI Life Sciences is a biotech company investing in psychedelic treatments for mental health disorders. | chat_gpt,claude,twitter,google |
| CMPS | Compass Pathways is at the forefront of psychedelic research, focusing on psilocybin therapy for depression. | chat_gpt,claude,twitter,google |
| GHRS | GH Research is developing a novel therapeutic approach using 5-MeO-DMT for treatment-resistant depression. | chat_gpt,twitter |
| JNJ | Johnson & Johnson's subsidiary Janssen Pharmaceuticals developed Spravato, a ketamine-based treatment for depression, indicating indirect benefits from the psychedelic trend. | chat_gpt |
| LLY | Eli Lilly, known for psychiatric drugs, might explore psychedelic-based treatments, benefiting indirectly from the trend. | chat_gpt |
| MNMD | Mind Medicine is researching various psychedelic substances for treatment of mental illness, making it a direct beneficiary. | chat_gpt,claude,twitter,google |
| MRK | Merck has a history of innovation in mental health treatments and could potentially enter the psychedelic space. | chat_gpt |
| PFE | Pfizer, with its extensive research in mental health medication, could pivot to or benefit from psychedelic research indirectly. | chat_gpt |
| ACB |  | twitter |
| CGC |  | twitter |
| CRON |  | twitter |
| RLMD |  | twitter |
| TLRY |  | twitter |
<!--[[[end]]]-->

## License

<p>
This project is licensed under <a href="./LICENSE">AGPLv3</a>.
</p>


## Contributors

Thank you for your improvements! We appreciate all the contributions from the community.

<!--[[[cog
import cog
import json
with open('config.json') as file:
  config = json.load(file)
  repo = config['github_repo'].lower()
  cog.outl(f'<a href="https://github.com/gettilt/{repo}/graphs/contributors">')
  cog.outl(f'  <img src="https://contrib.rocks/image?repo=gettilt/{repo}" />')
  cog.outl('</a>')
]]]-->
<a href="https://github.com/gettilt/psychedelics/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=gettilt/psychedelics" />
</a>
<!--[[[end]]]-->

## Join Our Community

<a href="https://discord.gg/4vYMhRpaMY" target="_blank">
<img src="https://discord.com/api/guilds/1179775688421683220/widget.png?style=banner3" alt="">
</a>
