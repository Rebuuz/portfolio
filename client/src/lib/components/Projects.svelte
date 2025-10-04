<script lang="ts">
    import * as Card from "$lib/components/ui/card"; 
</script>

<section class="projects-section" id="projects">
    <div class="flex flex-col">
        <h2 class="text-center text-3xl text-rose-300 pb-4">projects</h2> 
        <p class="text-center text-[#333]">these are some of the projects i have made!</p>
    </div>

    <div class="grid grid-row grid-cols-3 gap-5 mt-20">
        <Card.Root class="border-primary text-center">
            <Card.Header>
                
                <Card.Title>Card Title</Card.Title>
                <Card.Description>Card Description</Card.Description>
            </Card.Header>
            <Card.Content>
                <p>Card Content</p>
            </Card.Content>
            <Card.Footer>
                <p>Card Footer</p>
            </Card.Footer>
        </Card.Root>
        <Card.Root>
            <Card.Header>
                <Card.Title>Card Title</Card.Title>
                <Card.Description>Card Description</Card.Description>
            </Card.Header>
            <Card.Content>
                <p>Card Content</p>
            </Card.Content>
            <Card.Footer>
                <p>Card Footer</p>
            </Card.Footer>
        </Card.Root>
        <Card.Root>
            <Card.Header>
                <Card.Title>Card Title</Card.Title>
                <Card.Description>Card Description</Card.Description>
            </Card.Header>
            <Card.Content>
                <p>Card Content</p>
            </Card.Content>
            <Card.Footer>
                <p>Card Footer</p>
            </Card.Footer>
        </Card.Root>
    </div>
</section>