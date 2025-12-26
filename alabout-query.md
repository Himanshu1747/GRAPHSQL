Technology Stack: WordPress + WPGraphQL + ACF

Slide 1: Reusable Core (The SEO Fragment)
Purpose: Every page on the site uses this to ensure search engines can index the content correctly. Use this fragment inside other queries.

GraphQL

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
Slide 2: Global Branding & Navigation
Focus: Header, Main Menu, and Site Identity.

Menu: Recursive structure for 3 levels of navigation.

Identity: Fetches Site Logo and Site Description.

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
Slide 3: Homepage (Main Content Hub)
Focus: Media-rich banners and Campaign Details.

Video: Fetches banner and main body background videos.

Journey: Includes icons and titles for the personal history section.

Call to Action: Fetches read-more and donation button objects.

GraphQL

query Homepage {
  page(id: "/", idType: URI) {
    id
    title
    seo { ...PageSEO }
    featuredImage { node { mediaItemUrl altText fileSize } }
    homepage {
      videoBanner { node { mediaItemUrl altText } }
      videoMain { node { mediaItemUrl altText } }
      videoText
      campaign {
        campaignTitle
        campaignImage { node { sourceUrl mediaItemUrl altText } }
        voteImage { node { sourceUrl mediaItemUrl altText } }
      }
      journeyDetails {
        journeytitle
        iconImage { node { mediaItemUrl altText } }
      }
      delivering {
        iconImage { node { sourceUrl mediaItemUrl altText } }
        fieldName
        fieldParagraph
      }
    }
  }
}
Slide 4: About & Endorsements
Focus: Personal story and Education.

Shelby Section: Personal biography and community list.

Education: Grid of fields with specific icons and descriptions.

GraphQL

query AboutAndEndorsements {
  aboutPage: page(id: "about", idType: URI) {
    shortIntro {
      shelby
      aboutShelby
      shelbyImage { node { mediaItemUrl altText } }
    }
  }
  endorsementsPage: page(id: "life-experience", idType: URI) {
    endorsements {
      educationTitle
      eductaionField {
        fieldParagraph
        fieldType
        iconImage { node { mediaItemUrl altText } }
      }
    }
  }
}
Slide 5: Policy & Contact Utilities
Focus: Issues and User Communication.

Policy: Returns a list of visions and policy details.

Contact: Layout assets for the contact form page.

GraphQL

query PoliciesAndContact {
  proposedPage: page(id: "proposedlegislativeandpolicychanges", idType: URI) {
    proposed {
      congressTitle
      issuesWeStandFor {
        visionTitle
        vision_details
      }
    }
  }
  contactPage: page(id: "contact", idType: URI) {
    contactForm {
      mainTitle
      contactParagraph
      contactVoteImage { node { mediaItemUrl altText } }
    }
  }
}
Slide 6: Dynamic Widgets (Footer & Modals)
Focus: Site-wide utilities.

Footer: Custom widgets with text and menu items.

Popup: Content for the email/donation overlay modal.

GraphQL

query Widgets {
  footerBuilderWidget1 {
    title
    content
    menu_items { label url target }
  }
  popupData: page(id: "popup", idType: URI) {
    popup {
      mainTitle
      donateButton { url title }
      shelbyImage { node { mediaItemUrl } }
    }
  }
}