<script>
  import './button.css';
  import { createEventDispatcher } from 'svelte';
  /**
   * Is this the principal call to action on the page?
   */
  export let primary = false;

  /**
   * What background color to use
   */
  export let backgroundColor;
  /**
   * How large should the button be?
   */
  export let size = 'medium';
  /**
   * Button contents
   */
  export let label = '';

  let mode = primary ? 'storybook-button--primary' : 'storybook-button--secondary';

  let style = backgroundColor ? `background-color: ${backgroundColor}` : '';

  const dispatch = createEventDispatcher();

  /**
   * Optional click handler
   */
  function onClick(event) {
    dispatch('click', event);
  }
</script>

<!--
  Button component.

  This docblock doesn't appear because of the `{#if size === 'medium'}` line.
  Removing the button from the if block fixes the issue.

  @component
-->

{#if size === 'medium'}
  <button
    type="button"
    class={['storybook-button', `storybook-button--${size}`, mode].join(' ')}
    {style}
    on:click={onClick}>
    {label}
  </button>
{/if}
