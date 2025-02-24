# <% moment(tp.file.title).startOf('isoWeek').format('MMM DD') %> -   <% moment(tp.file.title).endOf('isoWeek').format('MMM DD') %>

# Goals this Week
- [ ]  
# Days

## [[Journal/Daily/<% moment(tp.file.title).startOf('isoWeek').add(0,'day').format('YYYY-MM-DD') %> |Monday]]
## [[Journal/Daily/<% moment(tp.file.title).startOf('isoWeek').add(1,'day').format('YYYY-MM-DD') %> |Tuesday]]
## [[Journal/Daily/<% moment(tp.file.title).startOf('isoWeek').add(2,'day').format('YYYY-MM-DD') %> |Wednesday]]
## [[Journal/Daily/<% moment(tp.file.title).startOf('isoWeek').add(3,'day').format('YYYY-MM-DD') %> |Thursday]]
## [[Journal/Daily/<% moment(tp.file.title).startOf('isoWeek').add(4,'day').format('YYYY-MM-DD') %> |Friday]]
## [[Journal/Daily/<% moment(tp.file.title).startOf('isoWeek').add(5,'day').format('YYYY-MM-DD') %> |Saturday]]
## [[Journal/Daily/<% moment(tp.file.title).startOf('isoWeek').add(6,'day').format('YYYY-MM-DD') %> |Sunday]]

```dataview
table without id
	file.link AS "Day",
	Gym AS "🏋️‍♂️",
	Mood AS "👨‍⚕️",
	choice(No_nap, "✅","❌") AS "😴",
	choice(Programming, "✅","❌") AS "🖥️",
	choice(Reading, "✅","❌") AS "📖️",
	Sleep as "🛏️",
	Weight as "⚖️"
from "Journal/Daily"
where Week = "<% moment(tp.file.title).format('gggg-[W]ww') %>"
```