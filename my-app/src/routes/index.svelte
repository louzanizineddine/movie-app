<script context="module">
    export async function load({fetch}) {
        const res = await fetch("https://api.themoviedb.org/3/movie/popular?api_key=27c689dd8b32b02b2db271915575bf32&language=en-US&page=1")
        const data = await res.json();
        console.log(data)
        if (res.ok) {
            return {
                props: { popular: data.results }
            }
        }
    }
</script>

<script>
    import PopularMoves from "../components/PopularMoves.svelte";
    import SearchMovies from "../components/SearchMovies.svelte";
    export let popular;
    import global from '../global.css'
    console.log(popular)
</script>

<section>
    <SearchMovies />
    <PopularMoves {popular}/>
</section>

