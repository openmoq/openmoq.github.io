<script lang="ts">
  import Badge from "$lib/Badge.svelte";
  import Container from "$lib/Container.svelte";
  import GridList from "$lib/GridList.svelte";
  import GridListItem from "$lib/GridListItem.svelte";
  import Section from "$lib/Section.svelte";
  import Subtitle from "$lib/Subtitle.svelte";
  import Text from "$lib/Text.svelte";
  import Title from "$lib/Title.svelte";

  const foundationData = [
    {
      title: "IETF QUIC protocol, RFC 9000",
      description:
        '<a href="https://www.rfc-editor.org/rfc/rfc9000.html" target="_blank" rel="noopener noreferrer" class="link">QUIC</a>: A UDP-Based Multiplexed and Secure Transport. QUIC is a modern, general-purpose transport layer network protocol standardized by the IETF to provide faster, more secure, and more reliable connections compared to traditional TCP. It operates on top of User Datagram Protocol (UDP) and integrates encryption (TLS 1.3) directly into its connection handshake, reducing latency and mitigating head-of-line blocking.',
    },
    {
      title: "IETF Media Over QUIC Transport",
      description:
        '<a href="https://datatracker.ietf.org/doc/draft-ietf-moq-transport" target="_blank" rel="noopener noreferrer">MOQT</a>: Media over QUIC Transport (MOQT) is a publish/subscribe protocol that runs over QUIC and WebTransport. MOQT leverages the features of these transports, such as streams, datagrams, priorities, and partial reliability. MOQT operates both point-to-point and through intermediate relays, enabling scalable low-latency delivery.',
    },
    {
      title: "IETF WebTransport",
      description:
        '<a href="https://datatracker.ietf.org/doc/draft-ietf-webtrans-overview" target="_blank" rel="noopener noreferrer">WebTransport</a> enables clients constrained by the Web security model to communicate with a remote server using a secure multiplexed transport.  It consists of a set of individual protocols that are safe to expose to untrusted applications, combined with an abstract model that allows them to be used interchangeably.',
    },
    {
      title: "W3C WebTransport",
      description:
        'A <a href="https://w3c.github.io/webtransport" target="_blank" rel="noopener noreferrer">Web API</a> enabling IETF WebTransport access in modern browsers, allowing web applications to establish interactive, bidirectional, multiplexed network connections.',
    },
  ];

  const smartMediaData = [
    "Pub/sub model for efficient distribution",
    "Fine-grained prioritization",
    "Adaptive quality based on network conditions",
    "Support for interactive and live content",
  ];
</script>

<Section background="white" id="technology">
  <Container>
    <div class="header">
      <div>
        <div class="badge">
          <Badge color="dark" className="mb-30">What is MOQ?</Badge>
        </div>
        <Title
          level={2}
          color="dark"
          size={40}
          weight={400}
          className="mb-10"
          maxWidth={530}
          align="center"
        >
          MOQ: Balancing Latency, Scale & Complexity
        </Title>
        <Text
          color="secondary-accent"
          weight={400}
          size={13}
          uppercase
          font="lexend-deca"
          align="center"
        >
          Tunable Latency Regimes + Broadcast Scale + Robust Architecture
        </Text>
      </div>
      <div>
        <Text
          color="dark"
          size={16}
          weight={400}
          opacity={0.8}
          className="mb-20"
        >
          MOQ is the next evolution in streaming protocols, designed for modern
          live, real-time, and on-demand applications. It is built upon a number
          of foundational standards and technologies developed by the Internet
          Engineering Task Force (IETF) and the World Wide Web Consortium (W3C)
          and detailed in the table below.
        </Text>
        <Text
          color="dark"
          size={16}
          weight={400}
          opacity={0.8}
          className="mb-20"
        >
          It provides a foundation that unifies low-latency interactivity with
          scalability and flexibility, supporting both live and non-real-time
          scenarios such as caching, time-shifted playback, and VOD.
        </Text>
        <Text color="dark" size={16} weight={400} opacity={0.8}>
          MOQ is built to balance the trade-offs between latency, scale, and
          complexity without forcing compromises.
        </Text>
      </div>
    </div>
    <div class="section">
      <Subtitle level={3}>Foundational standards and specifications</Subtitle>
      <GridList columns={2}>
        {#each foundationData as item (item.title)}
          <GridListItem color="light">
            <Text
              tag="strong"
              color="dark"
              size={18}
              weight={500}
              className="mb-10"
              font="lexend"
            >
              {item.title}
            </Text>
            <Text color="dark" size={16} weight={400} opacity={0.6}>
              <!-- eslint-disable-next-line svelte/no-at-html-tags -->
              {@html item.description}
            </Text>
          </GridListItem>
        {/each}
      </GridList>
    </div>
    <div>
      <Subtitle level={3}>Smart Media Delivery</Subtitle>
      <GridList columns={4}>
        {#each smartMediaData as item (item)}
          <GridListItem color="light">
            <Text
              tag="strong"
              color="dark"
              size={18}
              weight={500}
              font="lexend"
            >
              {item}
            </Text>
          </GridListItem>
        {/each}
      </GridList>
    </div>
  </Container>
</Section>

<style>
  .badge {
    display: flex;
    justify-content: center;
  }

  .header {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 20px;
    padding-top: 50px;
    max-width: 620px;
    margin: 0 auto 40px;
  }

  .section {
    margin-bottom: 30px;

    --color-link: var(--color-yellow--darker);
  }

  @media (min-width: 768px) {
    .header {
      padding-top: 70px;
      margin-bottom: 80px;
      gap: 40px;
    }

    .section {
      margin-bottom: 60px;
    }
  }
</style>
