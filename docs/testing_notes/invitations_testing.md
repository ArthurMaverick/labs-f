for user forecastable_test_2, use opportunity_id fa3923dd-58d7-4838-aa80-404726c54a07, buyer_map_id bd119338-12e5-40d4-b7dc-9f366e9fc8ef

select o.id, o.name, a.name as Account_Name  from opportunities o inner join buying_groups bg on o.buying_group_id = bg.id inner join accounts a on bg.account_id = a.id inner join subscribers s on s.id = a.subscriber_id;

 fa3923dd-58d7-4838-aa80-404726c54a07 | Pfizer Deal          | Southern Community Fincl Corp                | 0fef7919-da6d-4a08-be72-13b118e151b2


mutation inviteUserToBuyersMapMutation($input: InviteUserToBuyersMapInput!) {
  inviteUserToBuyersMap(input: $input) {
    clientMutationId
  }
}

{
  "input": {
      "emailsToInvite": ["vish_graphql_test_email@forecastable.com"],
      "opportunityId": "fa3923dd-58d7-4838-aa80-404726c54a07",
      "buyersMapId": "bd119338-12e5-40d4-b7dc-9f366e9fc8ef",
      "buyersMapLink": "mylink"
  }
}

mutation UpdateContactMutation(
  $input: UpdateContactInput!
) {
  updateContact(input: $input) {
    contact {
      id
      supportStatus
      sfdcContact {
        id
        sfdcId
      }
    }
  }
}

{
    "input": {
      "id": "Q29udGFjdDpjNDExYTAyZC1mNjUyLTRmNTctODYxMi03ZjZjYjMxMzM4YTM=",
      "fullName": "Bari Bradford McRobbi",
      "email": "spoon98@gmail.com",
      "functionalRole": "Sales Leader",
      "phoneNumber": "992-392-3839",
      "location": "Orlando",
      "currentTitle": "Teddy Bear Teddy Bear turn around"
    }
  }
