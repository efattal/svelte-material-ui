<div
  use:useActions={use}
  use:forwardEvents
  class="smui-button__group {className}"
  class:smui-button__group--raised={variant === 'raised'}
  {...exclude($$props, ['use', 'class', 'variant'])}
><slot></slot></div>

<script>
  import {setContext, getContext} from 'svelte';
  import {current_component} from 'svelte/internal';
  import {forwardEventsBuilder} from '@smui/common/forwardEvents.js';
  import {exclude} from '@smui/common/exclude.js';
  import {useActions} from '@smui/common/useActions.js';

  const forwardEvents = forwardEventsBuilder(current_component);

  export let use = [];
  let className = '';
  export {className as class};
  export let variant = 'text';
</script>