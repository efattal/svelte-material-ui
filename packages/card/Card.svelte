<div
  use:useActions={use}
  use:forwardEvents
  class="mdc-card {className}"
  class:mdc-card--outlined={variant === 'outlined'}
  class:smui-card--padded={padded}
  {...exclude($$props, ['use', 'class', 'variant', 'padded'])}
><slot></slot></div>

<script>
  import {current_component} from 'svelte/internal';
  import {forwardEventsBuilder} from '@smui/common/forwardEvents.js';
  import {exclude} from '@smui/common/exclude.js';
  import {useActions} from '@smui/common/useActions.js';

  const forwardEvents = forwardEventsBuilder(current_component);

  export let use = [];
  let className = '';
  export {className as class};
  export let variant = 'raised';
  export let padded = false;
</script>