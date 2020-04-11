# Minified Vue Timeline

Minified Vue Timeline is a minimalistic timeline component for vue-js.

## Installation

The usual ways:

```bash
npm i minified-vue-timeline
```

## Usage

```vue
import minifiedVueTimeline from "minified-vue-timeline";

<script>
components: {
  minifiedVueTimeline
},
</script>
```

## Examples

```vue
<template>
  <main>
    <minifiedVueTimeline :Timeline="Timeline" />
  </main>
</template>

<script>
import minifiedVueTimeline from "minified-vue-timeline";
export default {
  components: {
    minifiedVueTimeline
  },
  data() {
    return {
      Timeline: [
        {
          date: "29/10/1994",
          iconDotsColor: "#EE153B",
          history: [
            {
              name: "Application",
              summary: "Your Product Design application status was updated",
              time: "10:00am"
            },
            {
              name: "Job",
              summary: "Job Alert Created",
              time: "7:00am"
            },
            {
              name: "Inbox",
              summary: "New Message from Munrina Holmes",
              time: "5:00am"
            }
          ]
        },
        {
          date: "28/10/1994",
          iconDotsColor: "#7ED321",
          history: [
            {
              name: "Reminders",
              summary: "Interview with Mark starting in 2hrs",
              time: "5:50pm"
            },
            {
              name: "Inbox",
              summary: "New Message from Munrina Holmes",
              time: "3:20pm"
            }
          ]
        },
        {
          date: "27/10/1994",
          iconDotsColor: "#F5A623",
          history: [
            {
              name: "Reminders",
              summary: "Interview with Mark starting in 2hrs",
              time: "7:50pm"
            }
          ]
        }
      ]
    };
  }
};
</script>
```

## Data

| Option        | Types  | Required |         Description. |
| ------------- | :----: | :------: | -------------------: |
| Timeline      | Array  |   Yes    |                      |
| Date          | String |   Yes    |       TimeLine dates |
| iconDotsColor | String | optional |  Timeline dot colors |
| History       | Array  |   Yes    | Timeline Information |

## Props

| Option        |  Type  | Required | Description |
| ------------- | :----: | :------- | :---------- |
| TimelineColor | String | optional | Line color  |

## Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License

[MIT](https://choosealicense.com/licenses/mit/)
