<template>
	<article class="flex justify-center mt-8">
		<table class="border-2 border-black shadow-xl w-8/12 text-xl">
			<thead class="bg-green-600">
				<tr>
					<th class="py-3">#</th>
					<th class="py-3">Type</th>
					<th class="py-3">Name</th>
					<th class="py-3">Date</th>
					<th class="py-3">Amount</th>
					<th></th>
				</tr>
			</thead>
			<tbody class="text-center">
				<tr
					class="cursor-pointer border-2 border-black duration-300 bg-green-500"
					v-for="(expense, index) in expenses"
					:key="index"
				>
					<td class="py-3">
						{{ index + 1 }}
					</td>
					<td class="py-3">
						{{ expense.type }}
					</td>
					<td class="py-3">
						{{ expense.name }}
					</td>
					<td class="py-3">
						{{ expense.date }}
					</td>
					<td class="py-3">
                  ${{ expense.amount }}
               </td>
					<td>
						<img 
                     @click="removeExpense(index)"
                     class="w-5 h-5" 
                     src="../assets/x.png" 
                     alt="X" 
                  />
					</td>
				</tr>
			</tbody>
		</table>
	</article>
</template>

<script>
export default {
	name: 'ExpenseTable',
	props: {
		expenses: [],
	},
   methods: {
      removeExpense(index) {
         this.$emit("removeExpense", index);
      }
   }
};
</script>
