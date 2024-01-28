<script lang="ts">
  import { Route, Router } from "svelte-routing";
  import Layout from "./components/Layout.svelte";
  import Home from "./pages/Home.svelte";
  import Help from "./pages/Help.svelte";
  import NotFound from "./components/NotFound.svelte";
  import type { quizesType } from "./types";

  let quizes: quizesType[] = [
    { ques: "訪問", ans: "ほうもん" },
    { ques: "得恋", ans: "とくれん" },
    { ques: "歯医者", ans: "はいしゃ" },
  ];
</script>

<Router>
  <Layout>
    <Route path="/">
      <Home {quizes} />
    </Route>
    <Route path="/help">
      <Help {quizes}/>
    </Route>
    <Route path="/*" component={NotFound} />
  </Layout>
</Router>
