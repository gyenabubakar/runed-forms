<script lang="ts">
import { cn } from 'shadcn/utils.js';
import type { HTMLAttributes } from 'svelte/elements';
import type { WithElementRef } from 'shadcn/utils.js';

let {
	ref = $bindable(null),
	class: className,
	children,
	...restProps
}: WithElementRef<HTMLAttributes<HTMLParagraphElement>> = $props();
</script>

<p
	bind:this={ref}
	data-slot="card-description"
	class={cn('text-muted-foreground text-sm', className)}
	{...restProps}
>
	{@render children?.()}
</p>
