# --- REUSABLE SEO FRAGMENT ---
# Use this to keep page queries clean
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

# --- 1. GLOBAL NAVIGATION & SETTINGS ---
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

# --- 2. HOMEPAGE ---
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

# --- 3. ABOUT PAGE ---
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

# --- 4. ENDORSEMENTS / EXPERIENCE ---
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

# --- 5. PROPOSED POLICY ---
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

# --- 6. CONTACT PAGE ---
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

# --- 7. FOOTER & POPUP ---
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












RAW FORMATE I USED IN THE SITE 


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