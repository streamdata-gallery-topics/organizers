---
swagger: "2.0"
x-collection-name: LogMeIn
x-complete: 0
info:
  title: GoToMeeting Organizer
  description: Gets the individual organizer specified by the organizer's email address.
    If an email address is not specified, all organizers are returned. This API call
    is only available to users with the admin role.
  version: 1.0.0
host: api.getgo.com
basePath: /G2M/rest
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /groups/{groupkey}/organizers:
    get:
      summary: Organizers by group
      description: Returns all the organizers within a specific group. This API call
        is only available to users with the admin role.
      operationId: GroupsOrganizersByGroupkeyGet
      x-api-path-slug: groupsgroupkeyorganizers-get
      parameters:
      - in: header
        name: Accept
      - in: header
        name: Content-Type
      - in: path
        name: groupkey
      responses:
        200:
          description: OK
      tags:
      - Organizers
      - By
      - Group
  /organizers/{organizerKey}:
    get:
      summary: Organizer
      description: Gets the individual organizer specified by the organizer's email
        address. If an email address is not specified, all organizers are returned.
        This API call is only available to users with the admin role.
      operationId: OrganizersByOrganizerKeyGet
      x-api-path-slug: organizersorganizerkey-get
      parameters:
      - in: header
        name: Accept
      - in: header
        name: Content-Type
      - in: path
        name: organizerKey
      responses:
        200:
          description: OK
      tags:
      - Organizer
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