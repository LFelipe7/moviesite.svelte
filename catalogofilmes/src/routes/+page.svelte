<script context='module'>   
export async function load({ fetch }) {
    const rest = await fetch(
        'https://api.themoviedb.org/3/movie/popular?api_key=f0766485c60cf9fcc2f8dbef9b435ecc'
    );
    const data = await rest.json();
    if(rest.ok){
        return {
            props: {popular: data.results}
        }
    }
}
</script>

<script>
    import popularMovies from "./components/popularMovies.svelte"
    export let popular;
</script>

<section>
    <popularMovies {popular} />
</section>