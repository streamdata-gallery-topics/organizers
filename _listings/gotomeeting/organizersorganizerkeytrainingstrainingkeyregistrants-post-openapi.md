---
swagger: "2.0"
x-collection-name: GoToMeeting
x-complete: 0
info:
  title: Go To Training Register for Training
  description: 'Registers one person, identified by a unique email address, for a
    training. Approval is automatic unless payment or approval is required. The response
    contains the Confirmation page URL and Join URL for the registrant. NOTE: If some
    registrants do not receive a confirmation email, the emails could be getting blocked
    by their email server due to spam filtering or a grey-listing setting.'
  termsOfService: https://developer.citrixonline.com/terms-use
  contact:
    name: Developer Support
    url: https://developer.citrixonline.com
    email: developer-support@citrixonline.com
  version: 1.0.0
host: api.citrixonline.com
basePath: /G2T/rest
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /groups/{groupKey}/organizers:
    get:
      summary: Get organizers by group
      description: Returns all the organizers within a specific group. This API call
        is only available to users with the admin role.
      operationId: returns-all-the-organizers-within-a-specific-group--this-api-call-is-only-available-to-users-with-th
      x-api-path-slug: groupsgroupkeyorganizers-get
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Groups
      - GroupKey
      - Organizers
    post:
      summary: Create organizer in group
      description: Creates a new organizer and sends an email to the email address
        defined in request. This API call is only available to users with the admin
        role. You may also pass 'G2W' or 'G2T' or 'OPENVOICE' as productType variables,
        creating organizers for those products. A G2W or G2T organizer will also have
        access to G2M.
      operationId: creates-a-new-organizer-and-sends-an-email-to-the-email-address-defined-in-request--this-api-call-is
      x-api-path-slug: groupsgroupkeyorganizers-post
      parameters:
      - in: body
        name: body
        description: The details of the organizer to be created
        schema:
          $ref: '#/definitions/holder'
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Groups
      - GroupKey
      - Organizers
  /organizers:
    delete:
      summary: Delete organizer by email
      description: Deletes the individual organizer specified by the email address.
        This API call is only available to users with the admin role.
      operationId: deletes-the-individual-organizer-specified-by-the-email-address--this-api-call-is-only-available-to-
      x-api-path-slug: organizers-delete
      parameters:
      - in: query
        name: email
        description: The email address of the organizer
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Organizers
    get:
      summary: Get organizer by email / Get all organizers
      description: Gets the individual organizer specified by the organizer's email
        address. If an email address is not specified, all organizers are returned.
        This API call is only available to users with the admin role.
      operationId: gets-the-individual-organizer-specified-by-the-organizers-email-address--if-an-email-address-is-not-
      x-api-path-slug: organizers-get
      parameters:
      - in: query
        name: email
        description: The email address of the organizer
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Organizers
    post:
      summary: Create organizer
      description: Creates a new organizer and sends an email to the email address
        defined in the request. This API call is only available to users with the
        admin role. You may also pass 'G2W' or 'G2T' or 'OPENVOICE' as productType
        variables, creating organizers for those products. A G2W or G2T organizer
        will also have access to G2M.
      operationId: creates-a-new-organizer-and-sends-an-email-to-the-email-address-defined-in-the-request--this-api-cal
      x-api-path-slug: organizers-post
      parameters:
      - in: body
        name: body
        description: The details of the organizer to be created
        schema:
          $ref: '#/definitions/holder'
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Organizers
  /organizers/{organizerKey}:
    delete:
      summary: Delete organizer
      description: Deletes the individual organizer specified by the organizer key.
        This API call is only available to users with the admin role.
      operationId: deletes-the-individual-organizer-specified-by-the-organizer-key--this-api-call-is-only-available-to-
      x-api-path-slug: organizersorganizerkey-delete
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Organizers
      - OrganizerKey
    get:
      summary: Get organizer
      description: Returns the individual organizer specified by the key. This API
        call is only available to users with the admin role. Non-admin users can only
        make this call for their own organizerKey.
      operationId: returns-the-individual-organizer-specified-by-the-key--this-api-call-is-only-available-to-users-with
      x-api-path-slug: organizersorganizerkey-get
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Organizers
      - OrganizerKey
    put:
      summary: Update organizer
      description: Updates the products of the specified organizer. To add a product
        (G2M, G2W, G2T, OPENVOICE) for the organizer, the call must be sent once for
        each product you want to add. To remove all products for the organizer, set
        status to 'suspended'. The call is limited to users with the admin role.
      operationId: updates-the-products-of-the-specified-organizer--to-add-a-product-g2m-g2w-g2t-openvoice-for-the-orga
      x-api-path-slug: organizersorganizerkey-put
      parameters:
      - in: body
        name: body
        description: The organizers status
        schema:
          $ref: '#/definitions/holder'
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Organizers
      - OrganizerKey
  /organizers/{organizerKey}/attendees:
    get:
      summary: Get attendees by organizer
      description: Lists all attendees for all meetings within a specified date range
        for a specified organizer. This API call is only available to users with the
        admin role.
      operationId: lists-all-attendees-for-all-meetings-within-a-specified-date-range-for-a-specified-organizer--this-a
      x-api-path-slug: organizersorganizerkeyattendees-get
      parameters:
      - in: query
        name: endDate
        description: A required end of date range in ISO8601 UTC format, e
      - in: query
        name: No Name
      - in: query
        name: startDate
        description: A required start of date range in ISO8601 UTC format, e
      responses:
        200:
          description: OK
      tags:
      - Organizers
      - OrganizerKey
      - Attendees
  /organizers/{organizerKey}/historicalMeetings:
    get:
      summary: Get historical meetings by organizer
      description: 'Get historical meetings for the specified organizer that started
        within the specified date/time range. Remark: Meetings which are still ongoing
        at the time of the request are NOT contained in the result array.'
      operationId: get-historical-meetings-for-the-specified-organizer-that-started-within-the-specified-datetime-range
      x-api-path-slug: organizersorganizerkeyhistoricalmeetings-get
      parameters:
      - in: query
        name: endDate
        description: Required end of date range, in ISO8601 UTC format, e
      - in: query
        name: No Name
      - in: query
        name: startDate
        description: Required start of date range, in ISO8601 UTC format, e
      responses:
        200:
          description: OK
      tags:
      - Organizers
      - OrganizerKey
      - HistoricalMeetings
  /organizers/{organizerKey}/meetings:
    get:
      summary: 'DEPRECATED: Get meetings by organizer'
      description: 'DEPRECATED: Please use the new API calls ''Get historical meetings
        by organizer'' and ''Get upcoming meetings by organizer''. Gets future (scheduled)
        or past (history) meetings for a specified organizer. Include ''history=true''
        and the past start and end dates in the URL to retrieve past meetings. Enter
        ''scheduled=true'' (without dates) to get scheduled meetings.'
      operationId: deprecated-please-use-the-new-api-calls-get-historical-meetings-by-organizer-and-get-upcoming-meetin
      x-api-path-slug: organizersorganizerkeymeetings-get
      parameters:
      - in: query
        name: endDate
        description: If history is true, required end of date range, in ISO8601 UTC
          format, e
      - in: query
        name: history
        description: When true, returns all past meetings within date range
      - in: query
        name: No Name
      - in: query
        name: scheduled
        description: When true, returns all future meetings
      - in: query
        name: startDate
        description: If history is true, required start of date range, in ISO8601
          UTC format, e
      responses:
        200:
          description: OK
      tags:
      - Organizers
      - OrganizerKey
      - Meetings
  /organizers/{organizerKey}/upcomingMeetings:
    get:
      summary: Get upcoming meetings by organizer
      description: Get upcoming meetings for a specified organizer. This API call
        is only available to users with the admin role.
      operationId: get-upcoming-meetings-for-a-specified-organizer--this-api-call-is-only-available-to-users-with-the-a
      x-api-path-slug: organizersorganizerkeyupcomingmeetings-get
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Organizers
      - OrganizerKey
      - UpcomingMeetings
  /accounts/{accountKey}/organizers:
    get:
      summary: 'DEPRECATED: Get Organizers'
      description: 'DEPRECATED: Please use the Admin API call ''Get all users'' instead.
        For details see https://developer.citrixonline.com/get-all-users.'
      operationId: getAllOrganisers
      x-api-path-slug: accountsaccountkeyorganizers-get
      parameters:
      - in: path
        name: accountKey
        description: The key of the multi-user account
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Accounts
      - AccountKey
      - Organizers
  /organizers/{organizerKey}/trainings:
    get:
      summary: Get Trainings
      description: This call retrieves information on all scheduled trainings for
        a given organizer. The trainings are returned in the order in which they were
        created. Completed trainings are not included; ongoing trainings with past
        sessions are included along with the past sessions. If the organizer does
        not have any scheduled trainings, the response will be empty.
      operationId: getAllTrainings
      x-api-path-slug: organizersorganizerkeytrainings-get
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Organizers
      - OrganizerKey
      - Trainings
    post:
      summary: Create Training
      description: Schedules a training of one or more sessions. The call requires
        a training's name, at least one start and end time, and optionally may include
        additional sessions, a description, additional organizers (presenters), and
        registration settings. You can only add organizers to a training if you have
        a multi-user account. Once a training has been created with this method, you
        can accept registrations to the training. Registration is for the entire training
        - all sessions. (The GoToTraining admin site enables you to create trainings
        that allow participants to register for individual sessions as well as automatically
        create weekly or monthly events.) Registration settings controls whether you
        allow web registration for this training, and whether a confirmation email
        is sent to the registrant following registration. Disabling the confirmation
        email is an API-only setting. If the user registers through the GoToTraining
        website, a confirmation email is sent. If the user is manually approved by
        the training administrator through the GoToTraining web site, the confirmation
        email is sent. It is recommended that you disable web registration if you
        disable confirmation emails. The response contains a trainingKey for the scheduled
        training.
      operationId: scheduleTraining
      x-api-path-slug: organizersorganizerkeytrainings-post
      parameters:
      - in: body
        name: body
        description: The details of the training to create
        schema:
          $ref: '#/definitions/holder'
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Organizers
      - OrganizerKey
      - Trainings
  /organizers/{organizerKey}/trainings/{trainingKey}:
    delete:
      summary: Delete Training
      description: 'Deletes a scheduled or completed training. For scheduled trainings,
        it deletes all scheduled sessions of the training. For completed trainings,
        the sessions remain in the database. No email is sent to organizers or registrants,
        but when participants attempt to start or join the training, they are directed
        to a page that states: Training Not Found: The training you are trying to
        join is no longer available.'
      operationId: cancelTraining
      x-api-path-slug: organizersorganizerkeytrainingstrainingkey-delete
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Organizers
      - OrganizerKey
      - Trainings
      - TrainingKey
    get:
      summary: Get Training
      description: Uses the organizer key and training key to retrieve information
        on a scheduled training.
      operationId: getTraining
      x-api-path-slug: organizersorganizerkeytrainingstrainingkey-get
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Organizers
      - OrganizerKey
      - Trainings
      - TrainingKey
  /organizers/{organizerKey}/trainings/{trainingKey}/manageUrl:
    get:
      summary: Get Management URL for Training
      description: A request for a direct URL to the admin portal for a specific training.
        The request identifies the organizer and the training; the response provides
        a link the organizer can use to manage or launch the training in the admin
        portal. The training organizer will be required to log in. You can schedule
        and manage the training (e.g., add tests, polls and training materials) from
        the URL provided in the response.
      operationId: getManageTrainingURL
      x-api-path-slug: organizersorganizerkeytrainingstrainingkeymanageurl-get
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Organizers
      - OrganizerKey
      - Trainings
      - TrainingKey
      - ManageUrl
  /organizers/{organizerKey}/trainings/{trainingKey}/nameDescription:
    put:
      summary: Update Training Name and Description
      description: Request to update a scheduled training name and description.
      operationId: updateTrainingNameDescription
      x-api-path-slug: organizersorganizerkeytrainingstrainingkeynamedescription-put
      parameters:
      - in: body
        name: body
        description: The new name and description for the training
        schema:
          $ref: '#/definitions/holder'
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Organizers
      - OrganizerKey
      - Trainings
      - TrainingKey
      - NameDescription
  /organizers/{organizerKey}/trainings/{trainingKey}/organizers:
    get:
      summary: Get Training Organizers
      description: Retrieves organizer details for a specific training. This is only
        applicable to multi-user accounts with sharing enabled (co-organizers).
      operationId: getOrganisersForTraining
      x-api-path-slug: organizersorganizerkeytrainingstrainingkeyorganizers-get
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Organizers
      - OrganizerKey
      - Trainings
      - TrainingKey
      - Organizers
    put:
      summary: Update Training Organizers
      description: Replaces the co-organizers for a specific training. The scheduling
        organizer cannot be unassigned. Organizers will be notified via email if the
        notifyOrganizers parameter is set to true. Replaced organizers are not notified.
        This method is only applicable to multi-user accounts with sharing enabled
        (co-organizers).
      operationId: updateOrganisersForTraining
      x-api-path-slug: organizersorganizerkeytrainingstrainingkeyorganizers-put
      parameters:
      - in: body
        name: body
        description: The details of the training to create
        schema:
          $ref: '#/definitions/holder'
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Organizers
      - OrganizerKey
      - Trainings
      - TrainingKey
      - Organizers
  /organizers/{organizerKey}/trainings/{trainingKey}/registrants:
    get:
      summary: Get Training Registrants
      description: 'Retrieves details on all registrants for a specific training.
        Registrants can be:<br>WAITING - registrant registered and is awaiting approval
        (where organizer has required approval)<br>APPROVED - registrant registered
        and is approved<br>DENIED - registrant registered and was not approved.<br><br>IMPORTANT:
        The registrant data caches are typically updated immediately and the data
        will be returned in the response. However, the update can take as long as
        two hours.'
      operationId: getRegistrants
      x-api-path-slug: organizersorganizerkeytrainingstrainingkeyregistrants-get
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Organizers
      - OrganizerKey
      - Trainings
      - TrainingKey
      - Registrants
    post:
      summary: Register for Training
      description: 'Registers one person, identified by a unique email address, for
        a training. Approval is automatic unless payment or approval is required.
        The response contains the Confirmation page URL and Join URL for the registrant.
        NOTE: If some registrants do not receive a confirmation email, the emails
        could be getting blocked by their email server due to spam filtering or a
        grey-listing setting.'
      operationId: registerForTraining
      x-api-path-slug: organizersorganizerkeytrainingstrainingkeyregistrants-post
      parameters:
      - in: body
        name: body
        description: The details of the registrant to create
        schema:
          $ref: '#/definitions/holder'
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Organizers
      - OrganizerKey
      - Trainings
      - TrainingKey
      - Registrants
  /organizers/{organizerKey}/trainings/{trainingKey}/registrants/{registrantKey}:
    delete:
      summary: Cancel Registration
      description: This call cancels a registration in a scheduled training for a
        specific registrant. If the registrant has paid for the training, a cancellation
        cannot be completed with this method; it must be completed on the external
        admin site. No notification is sent to the registrant or the organizer by
        default. The registrant can re-register if needed.
      operationId: cancelRegistration
      x-api-path-slug: organizersorganizerkeytrainingstrainingkeyregistrantsregistrantkey-delete
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Organizers
      - OrganizerKey
      - Trainings
      - TrainingKey
      - Registrants
      - RegistrantKey
    get:
      summary: Get Registrant
      description: 'Retrieves details for specific registrant in a specific training.
        Registrants can be:<br>WAITING - registrant registered and is awaiting approval
        (where organizer has required approval)<br>APPROVED - registrant registered
        and is approved<br>DENIED - registrant registered and was not approved.<br><br>IMPORTANT:
        The registrant data caches are typically updated immediately and the data
        will be returned in the response. However, the update can take as long as
        two hours.'
      operationId: getRegistrant
      x-api-path-slug: organizersorganizerkeytrainingstrainingkeyregistrantsregistrantkey-get
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Organizers
      - OrganizerKey
      - Trainings
      - TrainingKey
      - Registrants
      - RegistrantKey
  /organizers/{organizerKey}/trainings/{trainingKey}/registrationSettings:
    put:
      summary: Update Training Registration Settings
      description: An API request to automatically enable or disable web registrations
        and confirmation emails to registrants.
      operationId: updateRegistrationSettingsForTraining
      x-api-path-slug: organizersorganizerkeytrainingstrainingkeyregistrationsettings-put
      parameters:
      - in: body
        name: body
        description: The new registration settings for the training
        schema:
          $ref: '#/definitions/holder'
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Organizers
      - OrganizerKey
      - Trainings
      - TrainingKey
      - RegistrationSettings
  /organizers/{organizerKey}/trainings/{trainingKey}/startUrl:
    get:
      summary: Get Start Url
      description: Returns a URL that can be used to start a training. When this URL
        is opened in a web browser, the GoToTraining client will be downloaded and
        launched and the training will start after the organizer logs in with its
        credentials.
      operationId: getStartUrl
      x-api-path-slug: organizersorganizerkeytrainingstrainingkeystarturl-get
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Organizers
      - OrganizerKey
      - Trainings
      - TrainingKey
      - StartUrl
  /organizers/{organizerKey}/trainings/{trainingKey}/times:
    put:
      summary: Update Training Times
      description: A request to update a scheduled training's start and end times.
        If the request contains 'notifyTrainers = true' and 'notifyRegistrants = true',
        both organizers and registrants are notified. The response provides the number
        of notified trainers and registrants.
      operationId: updateTrainingTimes
      x-api-path-slug: organizersorganizerkeytrainingstrainingkeytimes-put
      parameters:
      - in: body
        name: body
        description: The new start and end times for the scheduled training
        schema:
          $ref: '#/definitions/holder'
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Organizers
      - OrganizerKey
      - Trainings
      - TrainingKey
      - Times
  /reports/organizers/{organizerKey}/sessions:
    post:
      summary: Get Sessions by Date Range
      description: This call returns all session details over a given date range for
        a given organizer. A session is a completed training event.
      operationId: getSessionDetailsForDateRange
      x-api-path-slug: reportsorganizersorganizerkeysessions-post
      parameters:
      - in: body
        name: body
        description: The start and end times for the time range over which to retrieve
          training sessions
        schema:
          $ref: '#/definitions/holder'
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Reports
      - Organizers
      - OrganizerKey
      - Sessions
  /reports/organizers/{organizerKey}/sessions/{sessionKey}/attendees:
    get:
      summary: Get Attendance Details
      description: This call retrieves a list of registrants from a specific completed
        training session. The response includes the registrants' email addresses,
        and if they attended, it includes the duration of each period of their attendance
        in minutes, and the times at which they joined and left. If a registrant does
        not attend, they appear at the bottom of the listing with timeInSession =
        0.
      operationId: getAttendanceDetails
      x-api-path-slug: reportsorganizersorganizerkeysessionssessionkeyattendees-get
      parameters:
      - in: query
        name: No Name
      - in: path
        name: sessionKey
        description: The key of the training session
      responses:
        200:
          description: OK
      tags:
      - Reports
      - Organizers
      - OrganizerKey
      - Sessions
      - SessionKey
      - Attendees
  /reports/organizers/{organizerKey}/trainings/{trainingKey}:
    get:
      summary: Get Sessions By Training
      description: This call returns session details for a given training. A session
        is a completed training event. Each training may contain one or more sessions.
      operationId: getSessionDetailsForTraining
      x-api-path-slug: reportsorganizersorganizerkeytrainingstrainingkey-get
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Reports
      - Organizers
      - OrganizerKey
      - Trainings
      - TrainingKey
x-streamrank:
  polling_total_time_average: 0
  polling_size_download_average: 0
  streaming_total_time_average: 0
  streaming_size_download_average: 0
  change_yes: 0
  change_no: 0
  time_percentage: 0
  size_percentage: 0
  change_percentage: 0
  last_run: ""
  days_run: 0
  minute_run: 0
---