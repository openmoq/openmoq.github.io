<script lang="ts">
  import Container from "$lib/Container.svelte";
  import Section from "$lib/Section.svelte";
  import Text from "$lib/Text.svelte";
  import Title from "$lib/Title.svelte";

  import githubIcon from "$icons/github-outline.svg?raw";
  import Button from "$lib/Button.svelte";
  import GridList from "$lib/GridList.svelte";
  import GridListItem from "$lib/GridListItem.svelte";
  import Subtitle from "$lib/Subtitle.svelte";
  import Padding from "$lib/Padding.svelte";
  import { external } from "$lib/utils/routes";

  const benefits = [
    {
      title: "Tunable Latency Regimes",
      description:
        "From real-time to sub-second to VOD (any-latency streaming), even with a single media publisher",
    },
    {
      title: "Broadcast Scale",
      description: "Supports delivery across millions of sessions",
    },
    {
      title: "High Performance & Reliability",
      description: "Built by companies who run infrastructure at scale",
    },
    {
      title: "Robust Architecture",
      description: "Clean, maintainable, and flexible by design",
    },
    {
      title: "Open-Source Foundation",
      description: "What we build may be freely used by the industry",
    },
    {
      title: "Integrated Signaling",
      description:
        "Simplified and versatile configurations for greater reliability and ease of deployment",
    },
  ];
</script>

<Section background="light" overflow>
  <Container>
    <Padding tag="div" top={100} bottom={100} position="relative">
      <Title
        level={2}
        color="dark"
        size={40}
        weight={500}
        align="center"
        balance
        className="mb-20"
      >
        MOQ is designed for tunable latency regimes
      </Title>
      <Text
        color="dark"
        size={16}
        weight={400}
        opacity={0.6}
        align="center"
        className="mb-40"
      >
        From real-time interactive experiences to sub-second live streaming to
        on-demand playback.
      </Text>

      <div class="buttons mb-80">
        <Button href={external.demos} external withArrow>See MOQ in action</Button>
        <Button
          href={external.github}
          external
          icon={githubIcon}
          variant="secondary"
          color="dark"
        >
          Explore the code
        </Button>
      </div>

      <Subtitle level={3}>Key benefits of using MOQ</Subtitle>

      <GridList columns={3}>
        {#each benefits as benefit (benefit.title)}
          <GridListItem color="light">
            <Text
              tag="strong"
              color="dark"
              font="lexend"
              size={18}
              weight={500}
              className="mb-10"
            >
              {benefit.title}
            </Text>
            <Text color="dark" size={16} weight={400} opacity={0.6}>
              {benefit.description}
            </Text>
          </GridListItem>
        {/each}
      </GridList>
    </Padding>
  </Container>
</Section>

<style>
  .buttons {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
    justify-content: center;
  }
</style>
