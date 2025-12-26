Here is the full, raw content ready for your .md file. I have combined all queries and fragments into one clean document that any developer can copy and paste into their project.

Markdown

# GraphQL Queries Documentation

This file contains all the GraphQL queries used for the website's frontend development.

## Reusable Fragments
```graphql
fragment PageSEO on PostTypeSEO {
  title
  metaDesc
  focuskw
  canonical
  cornerstone
  fullHead
  metaRobotsNoindex
  metaRobotsNofollow
  opengraphTitle
  opengraphDescription
  opengraphImage { sourceUrl }
  opengraphType
  twitterTitle
  twitterDescription
  twitterImage { sourceUrl }
  schema { raw }
}
1. Global Components (Navigation, Footer, Popup)
Main Menu & Site Logo
GraphQL

query MainMenu {
  menu(id: "mainmenu", idType: SLUG) {
    menuItems {
      nodes {
        id
        label
        url
        uri
        parentId
        target
        order
        childItems {
          nodes {
            id
            label
            url
            parentId
            order
            uri
            childItems {
              nodes {
                id
                label
                url
              }
            }
          }
        }
      }
    }
  }
  siteLogo {
    sourceUrl
    altText
    mediaDetails { width height }
  }
  generalSettings {
    title
    description
  }
}
Footer Widgets & Popup
GraphQL

query FooterAndPopup {
  footerBuilderWidget1 {
    type
    title
    content
    image_url
    image_alt
    link_to
    menu_items { label url uri target }
  }
  page(id: "popup", idType: URI) {
    popup {
      backgroundImage { node { mediaItemUrl altText fileSize } }
      subTitle
      mainTitle
      donateButton { url title target }
      shelbyImage { node { mediaItemUrl altText fileSize } }
      logo { node { mediaItemUrl altText fileSize } }
    }
  }
}
2. Main Pages
Homepage
GraphQL

query Homepage {
  page(id: "/", idType: URI) {
    id
    title
    seo { ...PageSEO }
    featuredImage {
      node { mediaItemUrl altText fileSize }
    }
    homepage {
      videoBanner { node { mediaItemUrl altText } }
      videoMain { node { mediaItemUrl altText } }
      videoText
      congressTitle
      honestPolitician
      main
      paragraph
      readmore { url title target }
      campaign {
        campaignTitle
        campaignParagraph
        campaignImage { node { sourceUrl mediaItemUrl altText } }
        voteImage { node { sourceUrl mediaItemUrl altText } }
      }
      whyTrust
      shelbyTitle
      shelbyPargraph
      aboutShelbyButton { url title target }
      donateSupportButton { url title target }
      shelbyImage { node { sourceUrl mediaItemUrl altText } }
      shelbyVote { node { sourceUrl mediaItemUrl altText } }
      forThePeople
      mainTitle
      pargraphJourny
      journeyDetails {
        journeytitle
        iconImage { node { mediaItemUrl altText } }
      }
      deliveringTitle
      deliveringParagraph
      delivering {
        iconImage { node { sourceUrl mediaItemUrl altText } }
        fieldName
        fieldParagraph
      }
    }
  }
}
About Page
GraphQL

query AboutPage {
  page(id: "about", idType: URI) {
    title
    seo { ...PageSEO }
    featuredImage {
      node { mediaItemUrl altText fileSize }
    }
    shortIntro {
      whyTrust
      shelby
      aboutShelby
      shelbyImage { node { mediaItemUrl altText fileSize } }
      voteImage { node { mediaItemUrl altText fileSize } }
      community
      communityList
      politicianImage { node { mediaItemUrl altText fileSize } }
      politicianHeading
      politicianParagraph
      donateSupport { url title target }
      congressHeading
    }
  }
}
Endorsements / Life Experience
GraphQL

query Endorsements {
  page(id: "life-experience", idType: URI) {
    title
    seo { ...PageSEO }
    featuredImage {
      node { sourceUrl mediaItemUrl altText }
    }
    endorsements {
      shelbyPoint
      shelbyParagraph
      heyEveryone
      everyoneParagraph
      donateSupport { url title target }
      image1 { node { mediaItemUrl altText fileSize } }
      image2 { node { mediaItemUrl altText fileSize } }
      educationTitle
      eductaionField {
        fieldParagraph
        fieldType
        iconImage { node { mediaItemUrl altText fileSize } }
      }
      mainImage { node { mediaItemUrl altText fileSize } }
      mainTitle
      paragraph
      buttonlinks {
        buttonLinks { url title target }
      }
    }
  }
}
Proposed Policies
GraphQL

query Proposed {
  page(id: "proposedlegislativeandpolicychanges", idType: URI) {
    title
    seo { ...PageSEO }
    featuredImage {
      node { mediaItemUrl altText fileSize }
    }
    proposed {
      congressTitle
      guidingParagraph
      guidingImage { node { mediaItemUrl altText fileSize } }
      issuesWeStandFor {
        visionTitle
        vision_details
      }
    }
  }
}
Contact Page
GraphQL

query ContactPage {
  page(id: "contact", idType: URI) {
    title
    id
    seo { ...PageSEO }
    featuredImage {
      node { mediaItemUrl altText fileSize }
    }
    contactForm {
      mainTitle
      contactParagraph
      formMainTitle
      contactVoteImage { node { mediaItemUrl altText fileSize } }
    }
  }
}




##Raw code i used in astro js 

query MainMenu {
  menu(id: "mainmenu", idType: SLUG) {
    menuItems {
      nodes {
        id
        label
        url
        uri
        parentId
        target
        order
        childItems {
          nodes {
            id
            label
            url
            parentId
            order
            childItems {
              nodes {
                id
                label
                url
              }
            }
            uri
          }
        }
      }
    }
  }
  siteLogo {
    sourceUrl
    altText
    mediaDetails {
      width
      height
    }
  }
  generalSettings {
    title
    description
  }
}

query homepage {
  page(id: "/", idType: URI) {
    id
    title
    seo {
      title
      metaDesc
      focuskw
      canonical
      cornerstone
      fullHead
      metaRobotsNoindex
      metaRobotsNofollow
      opengraphTitle
      opengraphDescription
      opengraphImage {
        sourceUrl
      }
      opengraphType
      twitterTitle
      twitterDescription
      twitterImage {
        sourceUrl
      }
      schema {
        raw
      }
    }
    featuredImage {
      node {
        mediaItemUrl
        altText
        fileSize
      }
    }
    homepage {
      videoBanner {
        node {
          mediaItemUrl
          altText
        }
      }
      videoMain {
        node {
          mediaItemUrl
          altText
        }
      }
      videoText
      congressTitle
      honestPolitician
      main
      paragraph
      readmore {
        url
        title
        target
      }
      campaign {
        campaignTitle
        campaignParagraph
        campaignImage {
          node {
            sourceUrl
            mediaItemUrl
            altText
          }
        }
        voteImage {
          node {
            sourceUrl
            mediaItemUrl
            altText
          }
        }
      }
      whyTrust
      shelbyTitle
      shelbyPargraph
      aboutShelbyButton {
        url
        title
        target
      }
      donateSupportButton {
        url
        title
        target
      }
      shelbyImage {
        node {
          sourceUrl
          mediaItemUrl
          altText
        }
      }
      shelbyVote {
        node {
          sourceUrl
          mediaItemUrl
          altText
        }
      }
      forThePeople
      mainTitle
      pargraphJourny
      journeyDetails {
        journeytitle
        iconImage {
          node {
            mediaItemUrl
            altText
          }
        }
      }
      deliveringTitle
      deliveringParagraph
      delivering {
        iconImage {
          node {
            sourceUrl
            mediaItemUrl
            altText
          }
        }
        fieldName
        fieldParagraph
      }
    }
  }
}

query aboutpage {
  page(id: "about", idType: URI) {
    title
    seo {
      title
      metaDesc
      focuskw
      canonical
      cornerstone
      fullHead
      metaRobotsNoindex
      metaRobotsNofollow
      opengraphTitle
      opengraphDescription
      opengraphImage {
        sourceUrl
      }
      opengraphType
      twitterTitle
      twitterDescription
      twitterImage {
        sourceUrl
      }
      schema {
        raw
      }
    }
    featuredImage {
      node {
        mediaItemUrl
        altText
        fileSize
      }
    }
    shortIntro {
      whyTrust
      shelby
      aboutShelby
      shelbyImage {
        node {
          mediaItemUrl
          altText
          fileSize
        }
      }
      voteImage {
        node {
          mediaItemUrl
          altText
          fileSize
        }
      }
      community
      communityList
      politicianImage {
        node {
          mediaItemUrl
          altText
          fileSize
        }
      }
      politicianHeading
      politicianParagraph
      donateSupport {
        url
        title
        target
      }
      congressHeading
    }
  }
}

query endorsements {
  page(id: "life-experience", idType: URI) {
    title
    seo {
      title
      metaDesc
      focuskw
      canonical
      cornerstone
      fullHead
      metaRobotsNoindex
      metaRobotsNofollow
      opengraphTitle
      opengraphDescription
      opengraphImage {
        sourceUrl
      }
      opengraphType
      twitterTitle
      twitterDescription
      twitterImage {
        sourceUrl
      }
      schema {
        raw
      }
    }
    featuredImage {
      node {
        sourceUrl
        mediaItemUrl
        altText
      }
    }
    endorsements {
      shelbyPoint
      shelbyParagraph
      heyEveryone
      everyoneParagraph
      donateSupport {
        url
        title
        target
      }
      image1 {
        node {
          mediaItemUrl
          altText
          fileSize
        }
      }
      image2 {
        node {
          mediaItemUrl
          altText
          fileSize
        }
      }
      educationTitle
      eductaionField {
        fieldParagraph
        fieldType
        iconImage {
          node {
            mediaItemUrl
            altText
            fileSize
          }
        }
      }
      mainImage {
        node {
          mediaItemUrl
          altText
          fileSize
        }
      }
      mainTitle
      paragraph
      buttonlinks {
        buttonLinks {
          url
          title
          target
        }
      }
    }
  }
}

query Proposed {
  page(id: "proposedlegislativeandpolicychanges", idType: URI) {
    title
    seo {
      title
      metaDesc
      focuskw
      canonical
      cornerstone
      fullHead
      metaRobotsNoindex
      metaRobotsNofollow
      opengraphTitle
      opengraphDescription
      opengraphImage {
        sourceUrl
      }
      opengraphType
      twitterTitle
      twitterDescription
      twitterImage {
        sourceUrl
      }
      schema {
        raw
      }
    }
    featuredImage {
      node {
        mediaItemUrl
        altText
        fileSize
      }
    }
    proposed {
      congressTitle
      guidingParagraph
      guidingImage {
        node {
          mediaItemUrl
          altText
          fileSize
        }
      }
      issuesWeStandFor {
        visionTitle
        vision_details
      }
    }
  }
}

query contactform {
  page(id: "contact", idType: URI) {
    title
    id
    seo {
      title
      metaDesc
      focuskw
      canonical
      cornerstone
      fullHead
      metaRobotsNoindex
      metaRobotsNofollow
      opengraphTitle
      opengraphDescription
      opengraphImage {
        sourceUrl
      }
      opengraphType
      twitterTitle
      twitterDescription
      twitterImage {
        sourceUrl
      }
      schema {
        raw
      }
    }
    featuredImage {
      node {
        mediaItemUrl
        altText
        fileSize
      }
    }
    contactForm {
      mainTitle
      contactParagraph
      formMainTitle
      contactVoteImage {
        node {
          mediaItemUrl
          altText
          fileSize
        }
      }
    }
  }
}

query GetAllWidgetData {
  footerBuilderWidget1 {
    type
    title
    content
    image_url
    image_alt
    link_to
    menu_items {
      label
      url
      uri
      target
    }
  }
}

query popupdata{
page(id: "popup", idType: URI) {
  popup{
    backgroundImage{
      node{
         mediaItemUrl
        altText
        fileSize
      }
    }
    subTitle
    mainTitle
    donateButton{
       url
        title
        target
    }
    shelbyImage{
      node{
         mediaItemUrl
        altText
        fileSize
      }
    }
    
    logo{
      node{
         mediaItemUrl
        altText
        fileSize
      }
    }
    
  }

}
}