<template>
    <footer class="footer">
        <div class="container">
            <span v-html="$static.General.edges[0].node.footer"></span>
        </div>
    </footer>
</template>
<static-query>
query {
  General:allStrapiGeneral {
    edges {
      node {
        footer
      }
    }
  }
}
</static-query>
<script>
export default {
    data() {
        return {
            
        }
    }
}
</script>

<style scoped>
.footer {
    font-size: 0.8rem;
    padding: 6rem 0;
}
</style>
