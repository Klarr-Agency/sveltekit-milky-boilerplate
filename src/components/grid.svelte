<script>
	import Icon from '../components/icon.svelte';
	import Checkbox from '../components/checkbox.svelte';
	let gridItem = [
		{
			id: 1,
			title: 'Poutine',
			categorie: 'Food',
			author: 'Warwick',
			img: '../poutine.jpeg'
		}
	];

	// Holds table sort state.  Initialized to reflect table sorted by id column ascending.
	let sortBy = { col: 'id', ascending: true };

	$: sort = (column) => {
		if (sortBy.col == column) {
			sortBy.ascending = !sortBy.ascending;
		} else {
			sortBy.col = column;
			sortBy.ascending = true;
		}

		// Modifier to sorting function for ascending or descending
		let sortModifier = sortBy.ascending ? 1 : -1;

		let sort = (a, b) =>
			a[column] < b[column] ? -1 * sortModifier : a[column] > b[column] ? 1 * sortModifier : 0;

		gridItem = gridItem.sort(sort);
	};
</script>

<div class="grid">
	<table class="grid__table">
		<thead>
			<tr>
				<th class="grid__headerCell">
					<Checkbox bind:checkboxValue={gridItem} />
				</th>
				<th class="grid__headerCell" on:click={() => sort('title')}>Title</th>
				<th class="grid__headerCell" on:click={() => sort('author')}>Author</th>
				<th class="grid__headerCell">Preview</th>
			</tr>
		</thead>
		<tbody>
			{#each gridItem as row}
				<tr class="grid__row">
					<td class="grid__cell">
						<Checkbox bind:checkboxValue={row.id} />
					</td>
					<td class="grid__cell">
						<button class="cell__link">
							<div class="cell__preview">
								<img class="cell__img" src={row.img} alt={row.img_description} />
							</div>
							<div class="cell__details">
								<p class="cell__title">{row.title}</p>
								<p class="cell__category">{row.categorie}</p>
							</div>
						</button>
					</td>
					<td class="grid__cell">{row.author}</td>
					<td class="grid__cell">
						<button class="iconBtn">
							<Icon iconName={'preview'} />
						</button>
					</td>
				</tr>
			{/each}
		</tbody>
	</table>
</div>

<style lang="scss">
	.iconBtn {
		cursor: pointer;
		background-color: transparent;
		padding: 0;
		border: 0;
		border-radius: 50%;
		transition: box-shadow 0.25s, -webkit-box-shadow 0.25s;
		height: 48px;
		width: 48px;
		&:hover {
			box-shadow: 0 12px 20px rgb(0 0 0 / 25%);
		}
	}
	.grid {
		&__table {
			color: #fff;
			border-collapse: collapse;
			width: 100%;
		}
		&__row {
			border: 0;
		}
		&__headerCell {
			cursor: pointer;
			color: #b2b3bd;
			padding-top: 24px;
			padding-bottom: 24px;
			padding-left: 20px;
			text-align: left;
			font-size: 13px;
			line-height: 1.38462;
			font-weight: 400;
			font-family: var(--font-family);
			font-size: 14px;
			&:hover {
				color: var(--color-primary);
			}
		}
		&__cell {
			vertical-align: middle;
			padding-left: 20px;
			padding-top: 32px;
			padding-bottom: 32px;
			font-family: var(--font-family);
			font-size: 14px;
			border: none;
			border-bottom: 1px solid #373854;
			&::first-letter {
				text-transform: capitalize;
			}
		}
	}
	.cell {
		$self: &;
		&__link {
			display: flex;
			align-items: center;
			background-color: transparent;
			cursor: pointer;
			text-align: left;
			padding: 0;
			border: 0;

			#{ $self }__preview {
				display: flex;
				align-items: center;
				justify-content: center;
				position: relative;
				flex-shrink: 0;
				margin-right: 12px;
				width: 96px;
				height: 72px;
				#{ $self }__img {
					display: block;
					border-radius: 8px;
					max-height: 100%;
					max-width: 100%;
				}
			}
			#{ $self }__title {
				color: #fff;
				font-size: 16px;
				line-height: 1.1875;
				font-weight: 400;
				margin: 0;
			}
			#{ $self }__category {
				color: #808191;
				font-size: 13px;
				font-weight: 400;
				line-height: 1.38462;
				margin: 0;
			}
		}
	}
</style>
