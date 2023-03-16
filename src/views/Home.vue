<template>
    <div>
        <TheHeader />
        <TheAbout />
        <Work/>
        <TheProjects />
        <TheContact />
    </div>
</template>

<!-- ----- ----- ----- ----- ----- ----- ----- VUE SCRIPT CONFIGURATION ----- ----- ----- ----- ----- ----- ----- -->

<script>
import TheHeader from '@/components/TheHeader'
import TheAbout from '@/components/TheAbout'
import Work from '@/components/Work'
import TheProjects from '@/components/TheProjects'
import TheContact from '@/components/TheContact'

export default {
    name: 'TheHome',
    components: {
        TheHeader,
        TheAbout,
        Work,
        TheProjects,
        TheContact
    },
}
</script>

<!-- ----- ----- ----- ----- ----- ----- ----- STYLESHEET CONFIGURATION ----- ----- ----- ----- ----- ----- ----- -->

<style lang="scss">
</style>