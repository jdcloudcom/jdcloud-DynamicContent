# Query Domain Name Bandwidth Flow

## **1. Description**

Query domain name flow bandwidth (bandwidth_flow)

## **2. Request Parameter**

| **Name**  | **Type** | **Compulsory or Not ** | **Description**                                                     |
| ---------- | -------- | ------------ | ------------------------------------------------------------ |
| username   | String   | Yes           | JD User Name pin                                                |
| signature  | String   | Yes           | User Signature, verify user's identity information through md5 method to ensure information security.</br> md5=date+username+secret key SecretKey; date: format is yyyymmdd; username: JD user name pin secret key: agreed between the Parties;</br> example: such as current date 2016-10-23, user pin: jcloud_00, user secret key SecretKey: e7a31b1c5ea0efa9aa2f29c6559f7d61, then the signature is MD5(20161023jcloud_00e7a31b1c5ea0efa9aa2f29c6559f7d61) |
| domain     | String   | Yes           | Queried domain name                                                   |
| appName     | String   |No         | Name of release point; the release point currently only supports single query  |
| streamName   | String   | No           | Stream name; the stream name currently supports querying single path stream name, and app must be included when querying the stream nameName        |
| start_time | String   | Yes          | Time format: yyyy-mm-dd   hh:mi Reference Example: 2016-12-14 07:00;     |
| end_time   | String   | No           | Not a compulsory parameter; if no parameter is uploaded, it is current time by default, the query time span cannot exceed 30 days  |
| time_point  | String   | Not           | Not compulsory parameter, shows whether the counted interval value is calculated by the start time (startTime) or the end time (endTime). For example, counting the bandwidth from 00:00 to 00:05, if it’s time_point: startTime, then the bandwidth of 0-5 minutes is counted to 0; if it’s time_point: endTime, the bandwidth of 0-5 minutes is counted to the 5 minutes point; and if the time_point is not uploaded, it is by default to count the time point with the value of endTime.  |
 

## **3. Return Parameter**

| **Name**  | **Description**                                        |
| --------- | ----------------------------------------------- |
| status    | It means whether the API request is successful or not, 0 means successful, others means failure |
| msg       | Note information, e.g. the reasons why task sending fails, etc.                |
| data      | Domain name information array                                    |
| bandwidth | Bandwidth, Unit: Mbps                                            |
| flow      | Flow, Unit: MB                                            |

 

## **4. Call Example**

- ### **Request Address**

https://opencdn.jcloud.com/api/live/bandwidth_flow

- ### **Request Example**

* json Format

https://opencdn.jcloud.com/api/live/bandwidth_flow
```
{
    "username" :" test_user ",
    "signature" :"f7e472560b470a8d1892ea57626390d6",
    "domain" :" play.live.com ",
    "start_time" :"2018-06-02 17:15,
    "end_time" :"2018-06-02  17:30"
}
```
- ### Return Example
```
{
    "username" :" test_user ",
    "signature" :" f7e472560b470a8d1892ea57626390d6",
    "domain" :" play.live.com",
    "start_time" :"2018-06-02  17:15",
    "end_time" :"2018-06-02 17:30"
}
{
    "status": 0,
    "msg": "Successful",
    "data": [
        {
            "2018-06-02 17:15": {
                " play.live.com ": {
                    "bandwidth": 6.1,
                    "flow": 228.88
                }
            }
        },
        {
            "2018-06-02 17:20": {
                " play.live.com ": {
                    "bandwidth": 122.07,
                    "flow": 4577.64
                }
            }
        },
        {
            "2018-06-02 17:25": {
                " play.live.com ": {
                    "bandwidth": 122.07,
                    "flow": 4577.64
                }
            }
        },
        {
            "2018-06-02 17:30": {
                " play.live.com ": {
                    "bandwidth": 115.97,
                    "flow": 4348.75
                }
            }
        }
    ]
}
```
