# code_test

# I think overall code is good. But I have few sugesstions to make it better.

# In refactor/app/respository/BookingRepository.php 

There is two function named getUsersJobs and getUsersJobsHistory these are almost common in implemenation there is minor difference that we can sort in single fucntion by passing an extra parameter or may be pagination is required in both functions. As getUserJobs is sounds like we are fetching multipule jobs for single user as well so ther is only once difference I can see in response that is return value in customer condition that can be sorted with an extra parameter.

In store function from line 136 to 174 I think this piece of code is doing validation for the user data. Why we are not using laravel validation / rules to save multipule if else condtions.


We can use better approch in response handling I have passed through multipule functions that are using multipule return response based on condtional data or different kind of response. In sense of API bnuilding or front end approach I think response should have same formatting or same kind of parameters but with different response or values.

In sense of syntax it would be like  

        $response = array (
            'type'   => $type,
            'job'    => $job,
            'status' => $status
        );

instead of 

        $response['type'] = $user_type;
        $response['job'] = $job;
        $response['status'] = 'success';