---
swagger: "2.0"
x-collection-name: GoToMeeting
x-complete: 0
info:
  title: Go To Webinar Get upcoming webinars
  description: Returns webinars scheduled for the future for the specified organizer
    and webinars of other organizers where the specified organizer is a co-organizer.
  termsOfService: https://developer.citrixonline.com/terms-use
  contact:
    name: Developer Support
    url: https://developer.citrixonline.com
    email: developer-support@citrixonline.com
  version: 1.0.0
host: api.citrixonline.com
basePath: /G2W/rest
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
  /organizers/{organizerKey}/historicalWebinars:
    get:
      summary: Get historical webinars
      description: Returns details for completed webinars for the specified organizer
        and completed webinars of other organizers where the specified organizer is
        a co-organizer.
      operationId: getHistoricalWebinars
      x-api-path-slug: organizersorganizerkeyhistoricalwebinars-get
      parameters:
      - in: query
        name: fromTime
        description: A required start of datetime range in ISO8601 UTC format, e
      - in: query
        name: No Name
      - in: query
        name: toTime
        description: A required end of datetime range in ISO8601 UTC format, e
      responses:
        200:
          description: OK
      tags:
      - Organizers
      - OrganizerKey
      - HistoricalWebinars
  /organizers/{organizerKey}/sessions:
    get:
      summary: Get organizer sessions
      description: Retrieve all completed sessions of all the webinars of a given
        organizer.
      operationId: getOrganizerSessions
      x-api-path-slug: organizersorganizerkeysessions-get
      parameters:
      - in: query
        name: fromTime
        description: A required start of datetime range in ISO8601 UTC format, e
      - in: query
        name: No Name
      - in: query
        name: toTime
        description: A required end of datetime range in ISO8601 UTC format, e
      responses:
        200:
          description: OK
      tags:
      - Organizers
      - OrganizerKey
      - Sessions
  /organizers/{organizerKey}/upcomingWebinars:
    get:
      summary: Get upcoming webinars
      description: Returns webinars scheduled for the future for the specified organizer
        and webinars of other organizers where the specified organizer is a co-organizer.
      operationId: getUpcomingWebinars
      x-api-path-slug: organizersorganizerkeyupcomingwebinars-get
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Organizers
      - OrganizerKey
      - UpcomingWebinars
  /organizers/{organizerKey}/webinars:
    get:
      summary: Get all webinars
      description: Returns webinars scheduled for the future for a specified organizer.
      operationId: getAllWebinars
      x-api-path-slug: organizersorganizerkeywebinars-get
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Organizers
      - OrganizerKey
      - Webinars
    post:
      summary: Create webinar
      description: 'Creates a single session webinar, a sequence of webinars or a
        series of webinars depending on the type field in the body: "single_session"
        creates a single webinar session, "sequence" creates a webinar with multiple
        meeting times where attendees are expected to be the same for all sessions,
        and "series" creates a webinar with multiple meetings times where attendees
        choose only one to attend. The default, if no type is declared, is single_session.
        A sequence webinar requires a "recurrenceStart" object consisting of a "startTime"
        and "endTime" key for the first webinar of the sequence, a "recurrencePattern"
        of "daily", "weekly", "monthly", and a "recurrenceEnd" which is the last date
        of the sequence (for example, 2016-12-01). A series webinar requires a "times"
        array with a discrete "startTime" and "endTime" for each webinar in the series.
        The call requires a webinar subject and description. The "isPasswordProtected"
        sets whether the webinar requires a password for attendees to join. If set
        to True, the organizer must go to Registration Settings at My Webinars (https://global.gotowebinar.com/webinars.tmpl)
        and add the password to the webinar, and send the password to the registrants.
        The response provides a numeric webinarKey in string format for the new webinar.
        Once a webinar has been created with this method, you can accept registrations.'
      operationId: createWebinar
      x-api-path-slug: organizersorganizerkeywebinars-post
      parameters:
      - in: body
        name: body
        description: The webinar details
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
      - Webinars
  /organizers/{organizerKey}/webinars/{webinarKey}:
    delete:
      summary: Cancel webinar
      description: Cancels a specific webinar. If the webinar is a series or sequence,
        this call deletes all scheduled sessions. To send cancellation emails to registrants
        set sendCancellationEmails=true in the request. When the cancellation emails
        are sent, the default generated message is used in the cancellation email
        body.
      operationId: cancelWebinar
      x-api-path-slug: organizersorganizerkeywebinarswebinarkey-delete
      parameters:
      - in: query
        name: No Name
      - in: query
        name: sendCancellationEmails
        description: Indicates whether cancellation notice emails should be sent
      responses:
        200:
          description: OK
      tags:
      - Organizers
      - OrganizerKey
      - Webinars
      - WebinarKey
    get:
      summary: Get webinar
      description: Retrieve information on a specific webinar. If the type of the
        webinar is 'sequence', a sequence of future times will be provided. Webinars
        of type 'series' are treated the same as normal webinars - each session in
        the webinar series has a different webinarKey. If an organizer cancels a webinar,
        then a request to get that webinar would return a '404 Not Found' error.
      operationId: getWebinar
      x-api-path-slug: organizersorganizerkeywebinarswebinarkey-get
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Organizers
      - OrganizerKey
      - Webinars
      - WebinarKey
    put:
      summary: Update webinar
      description: Updates a webinar. The call requires at least one of the parameters
        in the request body. The request completely replaces the existing session,
        series, or sequence and so must include the full definition of each as for
        the Create call. Set notifyParticipants=true to send update emails to registrants.
      operationId: updateWebinar
      x-api-path-slug: organizersorganizerkeywebinarswebinarkey-put
      parameters:
      - in: body
        name: body
        description: The webinar details
        schema:
          $ref: '#/definitions/holder'
      - in: query
        name: No Name
      - in: query
        name: notifyParticipants
        description: Defines whether to send notifications to participants
      responses:
        200:
          description: OK
      tags:
      - Organizers
      - OrganizerKey
      - Webinars
      - WebinarKey
  /organizers/{organizerKey}/webinars/{webinarKey}/attendees:
    get:
      summary: Get attendees for all webinar sessions
      description: Returns all attendees for all sessions of the specified webinar.
      operationId: getAttendeesForAllWebinarSessions
      x-api-path-slug: organizersorganizerkeywebinarswebinarkeyattendees-get
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Organizers
      - OrganizerKey
      - Webinars
      - WebinarKey
      - Attendees
  /organizers/{organizerKey}/webinars/{webinarKey}/audio:
    get:
      summary: Get audio information
      description: Retrieves the audio/conferencing information for a specific webinar.
      operationId: getAudioInformation
      x-api-path-slug: organizersorganizerkeywebinarswebinarkeyaudio-get
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Organizers
      - OrganizerKey
      - Webinars
      - WebinarKey
      - Audio
    post:
      summary: Update audio information
      description: Updates the audio/conferencing settings for a specific webinar
      operationId: updateAudioInformation
      x-api-path-slug: organizersorganizerkeywebinarswebinarkeyaudio-post
      parameters:
      - in: body
        name: body
        description: The audio/conferencing settings
        schema:
          $ref: '#/definitions/holder'
      - in: query
        name: No Name
      - in: query
        name: notifyParticipants
        description: Defines whether to send notifications to participants
      responses:
        200:
          description: OK
      tags:
      - Organizers
      - OrganizerKey
      - Webinars
      - WebinarKey
      - Audio
  /organizers/{organizerKey}/webinars/{webinarKey}/coorganizers:
    get:
      summary: Get co-organizers
      description: Returns the co-organizers for the specified webinar. The original
        organizer who created the webinar is filtered out of the list. If the webinar
        has no co-organizers, an empty array is returned. Co-organizers that do not
        have a GoToWebinar account are returned as external co-organizers. For those
        organizers no surname is returned.
      operationId: getCoorganizers
      x-api-path-slug: organizersorganizerkeywebinarswebinarkeycoorganizers-get
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Organizers
      - OrganizerKey
      - Webinars
      - WebinarKey
      - Coorganizers
    post:
      summary: Create co-organizers
      description: Creates co-organizers for the specified webinar. For co-organizers
        that have a GoToWebinar account you have to set the parameter 'external' to
        'false'. In this case you have to pass the parameter 'organizerKey' only.
        For co-organizers that have no GoToWebinar account you have to set the parameter
        'external' to 'true'. In this case you have to pass the parameters 'givenName'
        and 'email'. Since there is no parameter for 'surname' you should pass first
        and last name to the parameter 'givenName'.
      operationId: createCoorganizers
      x-api-path-slug: organizersorganizerkeywebinarswebinarkeycoorganizers-post
      parameters:
      - in: body
        name: body
        description: The co-organizer details
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
      - Webinars
      - WebinarKey
      - Coorganizers
  /organizers/{organizerKey}/webinars/{webinarKey}/coorganizers/{coorganizerKey}:
    delete:
      summary: Delete co-organizer
      description: Deletes an internal co-organizer specified by the coorganizerKey
        (memberKey).
      operationId: deleteCoorganizer
      x-api-path-slug: organizersorganizerkeywebinarswebinarkeycoorganizerscoorganizerkey-delete
      parameters:
      - in: query
        name: external
        description: By default only internal co-organizers (with a GoToWebinar account)
          can be deleted
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Organizers
      - OrganizerKey
      - Webinars
      - WebinarKey
      - Coorganizers
      - CoorganizerKey
  /organizers/{organizerKey}/webinars/{webinarKey}/coorganizers/{coorganizerKey}/resendInvitation:
    post:
      summary: Resend invitation
      description: Resends an invitation email to the specified co-organizer
      operationId: resendCoorganizerInvitation
      x-api-path-slug: organizersorganizerkeywebinarswebinarkeycoorganizerscoorganizerkeyresendinvitation-post
      parameters:
      - in: query
        name: external
        description: By default only internal co-organizers (with a GoToWebinar account)
          will retrieve the resent invitation email
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Organizers
      - OrganizerKey
      - Webinars
      - WebinarKey
      - Coorganizers
      - CoorganizerKey
      - ResendInvitation
  /organizers/{organizerKey}/webinars/{webinarKey}/meetingtimes:
    get:
      summary: Get webinar meeting times
      description: Retrieves the meeting times for a webinar.
      operationId: getWebinarMeetingTimes
      x-api-path-slug: organizersorganizerkeywebinarswebinarkeymeetingtimes-get
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Organizers
      - OrganizerKey
      - Webinars
      - WebinarKey
      - Meetingtimes
  /organizers/{organizerKey}/webinars/{webinarKey}/panelists:
    get:
      summary: Get webinar panelists
      description: Retrieves all the panelists for a specific webinar.
      operationId: getPanelists
      x-api-path-slug: organizersorganizerkeywebinarswebinarkeypanelists-get
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Organizers
      - OrganizerKey
      - Webinars
      - WebinarKey
      - Panelists
    post:
      summary: Create Panelists
      description: Create panelists for a specified webinar
      operationId: createPanelists
      x-api-path-slug: organizersorganizerkeywebinarswebinarkeypanelists-post
      parameters:
      - in: body
        name: body
        description: Array of panelists
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
      - Webinars
      - WebinarKey
      - Panelists
  /organizers/{organizerKey}/webinars/{webinarKey}/panelists/{panelistKey}:
    delete:
      summary: Delete webinar panelist
      description: Removes a webinar panelist.
      operationId: deleteWebinarPanelist
      x-api-path-slug: organizersorganizerkeywebinarswebinarkeypanelistspanelistkey-delete
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Organizers
      - OrganizerKey
      - Webinars
      - WebinarKey
      - Panelists
      - PanelistKey
  /organizers/{organizerKey}/webinars/{webinarKey}/panelists/{panelistKey}/resendInvitation:
    post:
      summary: Resend panelist invitation
      description: Resend the panelist invitation email.
      operationId: resendPanelistInvitation
      x-api-path-slug: organizersorganizerkeywebinarswebinarkeypanelistspanelistkeyresendinvitation-post
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Organizers
      - OrganizerKey
      - Webinars
      - WebinarKey
      - Panelists
      - PanelistKey
      - ResendInvitation
  /organizers/{organizerKey}/webinars/{webinarKey}/performance:
    get:
      summary: Get performance for all webinar sessions
      description: Gets performance details for all sessions of a specific webinar.
      operationId: getPerformanceForAllWebinarSessions
      x-api-path-slug: organizersorganizerkeywebinarswebinarkeyperformance-get
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Organizers
      - OrganizerKey
      - Webinars
      - WebinarKey
      - Performance
  /organizers/{organizerKey}/webinars/{webinarKey}/registrants:
    get:
      summary: Get registrants
      description: Retrieve registration details for all registrants of a specific
        webinar. Registrant details will not include all fields captured when creating
        the registrant. To see all data, use the API call 'Get Registrant'. Registrants
        can have one of the following states; <br>WAITING - registrant registered
        and is awaiting approval (where organizer has required approval), <br>APPROVED
        - registrant registered and is approved, and <br>DENIED - registrant registered
        and was denied.
      operationId: getAllRegistrantsForWebinar
      x-api-path-slug: organizersorganizerkeywebinarswebinarkeyregistrants-get
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Organizers
      - OrganizerKey
      - Webinars
      - WebinarKey
      - Registrants
    post:
      summary: Create registrant
      description: 'Register an attendee for a scheduled webinar. The response contains
        the registrantKey and join URL for the registrant. An email will be sent to
        the registrant unless the organizer turns off the confirmation email setting
        from the GoToWebinar website. Please note that you must provide all required
        fields including custom fields defined during the webinar creation. Use the
        API call ''Get registration fields'' to get a list of all fields, if they
        are required, and their possible values. At this time there are two versions
        of the ''Create Registrant'' call. The first version only accepts firstName,
        lastName, and email and ignores all other fields. If you have custom fields
        or want to capture additional information this version won''t work for you.
        The second version allows you to pass all required and optional fields, including
        custom fields defined when creating the webinar. To use the second version
        you must pass the header value ''Accept: application/vnd.citrix.g2wapi-v1.1+json''
        instead of ''Accept: application/json''. Leaving this header out results in
        the first version of the API call.'
      operationId: createRegistrant
      x-api-path-slug: organizersorganizerkeywebinarswebinarkeyregistrants-post
      parameters:
      - in: header
        name: Accept
        description: Set to application/vnd
      - in: body
        name: body
        description: The registrant details
        schema:
          $ref: '#/definitions/holder'
      - in: query
        name: No Name
      - in: query
        name: resendConfirmation
        description: Indicates whether the confirmation email should be resent when
          a registrant is re-registered
      responses:
        200:
          description: OK
      tags:
      - Organizers
      - OrganizerKey
      - Webinars
      - WebinarKey
      - Registrants
  /organizers/{organizerKey}/webinars/{webinarKey}/registrants/fields:
    get:
      summary: Get registration fields
      description: Retrieve required, optional registration, and custom questions
        for a specified webinar.
      operationId: getRegistrationFields
      x-api-path-slug: organizersorganizerkeywebinarswebinarkeyregistrantsfields-get
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Organizers
      - OrganizerKey
      - Webinars
      - WebinarKey
      - Registrants
      - Fields
  /organizers/{organizerKey}/webinars/{webinarKey}/registrants/{registrantKey}:
    delete:
      summary: Delete registrant
      description: Removes a webinar registrant from current registrations for the
        specified webinar. The webinar must be a scheduled, future webinar.
      operationId: deleteRegistrant
      x-api-path-slug: organizersorganizerkeywebinarswebinarkeyregistrantsregistrantkey-delete
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Organizers
      - OrganizerKey
      - Webinars
      - WebinarKey
      - Registrants
      - RegistrantKey
    get:
      summary: Get registrant
      description: Retrieve registration details for a specific registrant.
      operationId: getRegistrant
      x-api-path-slug: organizersorganizerkeywebinarswebinarkeyregistrantsregistrantkey-get
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Organizers
      - OrganizerKey
      - Webinars
      - WebinarKey
      - Registrants
      - RegistrantKey
  /organizers/{organizerKey}/webinars/{webinarKey}/sessions:
    get:
      summary: Get webinar sessions
      description: Retrieves details for all past sessions of a specific webinar.
      operationId: getAllSessions
      x-api-path-slug: organizersorganizerkeywebinarswebinarkeysessions-get
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Organizers
      - OrganizerKey
      - Webinars
      - WebinarKey
      - Sessions
  /organizers/{organizerKey}/webinars/{webinarKey}/sessions/{sessionKey}:
    get:
      summary: Get webinar session
      description: Retrieves attendance details for a specific webinar session that
        has ended. If attendees attended the session ('registrantsAttended'), specific
        attendance details, such as attendenceTime for a registrant, will also be
        retrieved. For technical reasons, this call cannot be executed from this documentation.
        Please use the curl command to execute it.
      operationId: getWebinarSession
      x-api-path-slug: organizersorganizerkeywebinarswebinarkeysessionssessionkey-get
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Organizers
      - OrganizerKey
      - Webinars
      - WebinarKey
      - Sessions
      - SessionKey
  /organizers/{organizerKey}/webinars/{webinarKey}/sessions/{sessionKey}/attendees:
    get:
      summary: Get session attendees
      description: Retrieve details for all attendees of a specific webinar session.
        For technical reasons, this call cannot be executed from this documentation.
        Please use the curl command to execute it.
      operationId: getAttendees
      x-api-path-slug: organizersorganizerkeywebinarswebinarkeysessionssessionkeyattendees-get
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Organizers
      - OrganizerKey
      - Webinars
      - WebinarKey
      - Sessions
      - SessionKey
      - Attendees
  /organizers/{organizerKey}/webinars/{webinarKey}/sessions/{sessionKey}/attendees/{registrantKey}:
    get:
      summary: Get attendee
      description: Retrieve registration details for a particular attendee of a specific
        webinar session. For technical reasons, this call cannot be executed from
        this documentation. Please use the curl command to execute it.
      operationId: getAttendee
      x-api-path-slug: organizersorganizerkeywebinarswebinarkeysessionssessionkeyattendeesregistrantkey-get
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Organizers
      - OrganizerKey
      - Webinars
      - WebinarKey
      - Sessions
      - SessionKey
      - Attendees
      - RegistrantKey
  /organizers/{organizerKey}/webinars/{webinarKey}/sessions/{sessionKey}/attendees/{registrantKey}/polls:
    get:
      summary: Get attendee poll answers
      description: Get poll answers from a particular attendee of a specific webinar
        session. For technical reasons, this call cannot be executed from this documentation.
        Please use the curl command to execute it.
      operationId: getAttendeePollAnswers
      x-api-path-slug: organizersorganizerkeywebinarswebinarkeysessionssessionkeyattendeesregistrantkeypolls-get
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Organizers
      - OrganizerKey
      - Webinars
      - WebinarKey
      - Sessions
      - SessionKey
      - Attendees
      - RegistrantKey
      - Polls
  /organizers/{organizerKey}/webinars/{webinarKey}/sessions/{sessionKey}/attendees/{registrantKey}/questions:
    get:
      summary: Get attendee questions
      description: Get questions asked by an attendee during a webinar session. For
        technical reasons, this call cannot be executed from this documentation. Please
        use the curl command to execute it.
      operationId: getAttendeeQuestions
      x-api-path-slug: organizersorganizerkeywebinarswebinarkeysessionssessionkeyattendeesregistrantkeyquestions-get
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Organizers
      - OrganizerKey
      - Webinars
      - WebinarKey
      - Sessions
      - SessionKey
      - Attendees
      - RegistrantKey
      - Questions
  /organizers/{organizerKey}/webinars/{webinarKey}/sessions/{sessionKey}/attendees/{registrantKey}/surveys:
    get:
      summary: Get attendee survey answers
      description: Retrieve survey answers from a particular attendee during a webinar
        session. For technical reasons, this call cannot be executed from this documentation.
        Please use the curl command to execute it.
      operationId: getAttendeeSurveyAnswers
      x-api-path-slug: organizersorganizerkeywebinarswebinarkeysessionssessionkeyattendeesregistrantkeysurveys-get
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Organizers
      - OrganizerKey
      - Webinars
      - WebinarKey
      - Sessions
      - SessionKey
      - Attendees
      - RegistrantKey
      - Surveys
  /organizers/{organizerKey}/webinars/{webinarKey}/sessions/{sessionKey}/performance:
    get:
      summary: Get session performance
      description: Get performance details for a session. For technical reasons, this
        call cannot be executed from this documentation. Please use the curl command
        to execute it.
      operationId: getPerformance
      x-api-path-slug: organizersorganizerkeywebinarswebinarkeysessionssessionkeyperformance-get
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Organizers
      - OrganizerKey
      - Webinars
      - WebinarKey
      - Sessions
      - SessionKey
      - Performance
  /organizers/{organizerKey}/webinars/{webinarKey}/sessions/{sessionKey}/polls:
    get:
      summary: Get session polls
      description: Retrieve all collated attendee questions and answers for polls
        from a specific webinar session. For technical reasons, this call cannot be
        executed from this documentation. Please use the curl command to execute it.
      operationId: getPolls
      x-api-path-slug: organizersorganizerkeywebinarswebinarkeysessionssessionkeypolls-get
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Organizers
      - OrganizerKey
      - Webinars
      - WebinarKey
      - Sessions
      - SessionKey
      - Polls
  /organizers/{organizerKey}/webinars/{webinarKey}/sessions/{sessionKey}/questions:
    get:
      summary: Get session questions
      description: Retrieve questions and answers for a past webinar session. For
        technical reasons, this call cannot be executed from this documentation. Please
        use the curl command to execute it.
      operationId: getQuestions
      x-api-path-slug: organizersorganizerkeywebinarswebinarkeysessionssessionkeyquestions-get
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Organizers
      - OrganizerKey
      - Webinars
      - WebinarKey
      - Sessions
      - SessionKey
      - Questions
  /organizers/{organizerKey}/webinars/{webinarKey}/sessions/{sessionKey}/surveys:
    get:
      summary: Get session surveys
      description: Retrieve surveys for a past webinar session. For technical reasons,
        this call cannot be executed from this documentation. Please use the curl
        command to execute it.
      operationId: getSurveys
      x-api-path-slug: organizersorganizerkeywebinarswebinarkeysessionssessionkeysurveys-get
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Organizers
      - OrganizerKey
      - Webinars
      - WebinarKey
      - Sessions
      - SessionKey
      - Surveys
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