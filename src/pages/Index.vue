<template>
  <Layout>
    <div class="container">
       <Hero />
       <ProjectsGrid :projects="$page.ProjectPost.edges" />
    </div>
    <LatestJournals :journals="$page.JournalPost.edges" />
  </Layout>
</template>
<page-query>
query {
  ProjectPost:allStrapiProjectPost {
    edges {
      node {
        id
        title
        date
      	content
        project_bg_color
        project_fg_color
				thumbnail {
          url
        }
        year
        categories {
          title
        }
      }
    }
  }
  JournalPost:allStrapiJournalPost{
    edges {
      node {
        id
        title
        date
        author
        excerpt
        content
      }
    }
  }
}
</page-query>

<script>
import Hero from "@/components/Hero"
import ProjectsGrid from "@/components/ProjectsGrid"
import LatestJournals from "@/components/LatestJournals"
export default {
  metaInfo: {
    title: 'Hello, world!'
  },
  data(){
    return {
      pro:[]
    }
  },
  components: {
    Hero,
    ProjectsGrid,
    LatestJournals
  }
}
</script>

<style>
.home-links a {
  margin-right: 1rem;
}
</style>
