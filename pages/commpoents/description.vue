<template lang="pug">
div.description.wow.animate__fadeInUp
  h2.wow.animate__fadeInDown.title DeRender Protocol Brief Description
  p In brief, how do we implement this? Lessors post an account for lease, which can be rented by multiple lessees. The availability of the account is determined by a collective vote among the lessees. If the majority votes the account as usable, it is deemed usable; if not, it is unusable. Non-voting defaults to usable. Payment of the rent is based on the final voting outcome. As both parties in a transaction are not entirely trustworthy, both must deposit a security during the transaction process. If a lessee votes contrary to the majority, they are deemed dishonest and will be fined. Lessees cannot predict the final voting result; thus, casting an honest vote is in their best interest. There are many more details available in our white paper.
</template>

<script>
</script>

<style lang="scss" scoped>
.description {
  width: 1200px;
  margin: 0 auto;
  p {
    text-indent: 100px;
    font-size: 24px;
  }
}
</style>
