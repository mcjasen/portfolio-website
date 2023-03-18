<template>
    <section id="work">
        <div class="section-header"><h1><span class="number">02.</span>Study & Work<span class="line"></span></h1></div>
        <div class="work-container">
            <WorkItem 
                date="September 2021" 
                title="Internship as Software Engineer"
                company="iC-Haus (microcontroller manufacture & design)"
                link="https://www.ichaus.de/about_us"
                :activities="['Developed a web-app to improve the shipping process']">
            </WorkItem>
            <WorkItem 
                date="October 2020 until February 2023" 
                title="Master of Science - Computer Science"
                company="University of Applied Sciences, Trier"
                link="https://www.hochschule-trier.de/en/computer-science/studies/ima"
                :activities="[]">
            </WorkItem>
            <WorkItem 
                date="October 2017 until September 2020" 
                title="Dual study - Bachelor of Science - Business Information Systems"
                company="Technische Werke Ludwigshafen (municipal utility)"
                link="https://www.twl.de/das-ist-twl/ueber-uns"
                :activities="['Developed a SAP-App to improve the procurment process', 'Developed a digital phone book  as a web-app']">
            </WorkItem>
            <WorkItem 
                date="October 2017 until September 2020" 
                title="Bachelor of Science - Business Information Systems"
                company="Baden-Wuerttemberg Cooperative State University (DHBW), Mannheim"
                link="https://www.mannheim.dhbw.de/en/dual-study/bachelors-degree-courses/business/business-information-systems/software-engineering"
                specialisation="Specialisation: Software Engineering">
            </WorkItem>
        </div>
    </section>
</template>

<script>
import WorkItem from '@/components/WorkItem'

export default{
    name: 'TheWork',
    components: {
        WorkItem
    }
}
</script>

<style lang="scss">
.work-container{
    margin-bottom: 200px;
}

@media (min-width: 801px){
    .work-container{
        display: grid;
        column-gap: 50px;
        row-gap: 20px;
        grid-template-columns: 1fr 1fr;
        background:linear-gradient(var(--timeline-color), var(--timeline-color)) center/1.5px 100% no-repeat;
    }
    
}

@media (max-width: 800px){
    .work-container{
        display: flex;
        flex-direction: column;
        row-gap: 30px;
    }
}

</style>