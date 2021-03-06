# StartTranscriptionJob<a name="API_StartTranscriptionJob"></a>

Starts an asynchronous job to transcribe speech to text\.

## Request Syntax<a name="API_StartTranscriptionJob_RequestSyntax"></a>

```
{
   "LanguageCode": "string",
   "Media": { 
      "MediaFileUri": "string"
   },
   "MediaFormat": "string",
   "MediaSampleRateHertz": number,
   "TranscriptionJobName": "string"
}
```

## Request Parameters<a name="API_StartTranscriptionJob_RequestParameters"></a>

For information about the parameters that are common to all actions, see Common Parameters\.

The request accepts the following data in JSON format\.

 ** LanguageCode **   
The language code for the language used in the input media file\.  
Type: String  
Valid Values:` en-US | es-US`   
Required: Yes

 ** Media **   
An object that describes the input media for a transcription job\.  
Type: [Media](API_Media.md) object  
Required: Yes

 ** MediaFormat **   
The format of the input media file\.  
Type: String  
Valid Values:` mp3 | mp4 | wav | flac`   
Required: Yes

 ** MediaSampleRateHertz **   
The sample rate, in Hertz, of the audio track in the input media file\.   
Type: Integer  
Valid Range: Minimum value of 8000\. Maximum value of 48000\.  
Required: No

 ** TranscriptionJobName **   
The name of the job\. The name must be unique within an AWS account\.  
Type: String  
Length Constraints: Minimum length of 1\. Maximum length of 200\.  
Pattern: `^[0-9a-zA-Z._-]+`   
Required: Yes

## Response Syntax<a name="API_StartTranscriptionJob_ResponseSyntax"></a>

```
{
   "TranscriptionJob": { 
      "CompletionTime": number,
      "CreationTime": number,
      "FailureReason": "string",
      "LanguageCode": "string",
      "Media": { 
         "MediaFileUri": "string"
      },
      "MediaFormat": "string",
      "MediaSampleRateHertz": number,
      "Transcript": { 
         "TranscriptFileUri": "string"
      },
      "TranscriptionJobName": "string",
      "TranscriptionJobStatus": "string"
   }
}
```

## Response Elements<a name="API_StartTranscriptionJob_ResponseElements"></a>

If the action is successful, the service sends back an HTTP 200 response\.

The following data is returned in JSON format by the service\.

 ** TranscriptionJob **   
An object containing details of the asynchronous transcription job\.  
Type: [TranscriptionJob](API_TranscriptionJob.md) object

## Errors<a name="API_StartTranscriptionJob_Errors"></a>

For information about the errors that are common to all actions, see [Common Errors](CommonErrors.md)\.

 **BadRequestException**   
There is a problem with one of the input fields\. Check the S3 bucket name, make sure that the job name is not a duplicate, and confirm that you are using the correct file format\. Then resend your request\.  
HTTP Status Code: 400

 **ConflictException**   
The `JobName` field is a duplicate of a previously entered job name\. Resend your request with a different name\.  
HTTP Status Code: 400

 **InternalFailureException**   
There was an internal error\. Check the error message and try your request again\.  
HTTP Status Code: 500

 **LimitExceededException**   
Either you have sent too many requests or your input file is longer than 2 hours\. Wait before you resend your request, or use a smaller file and resend the request\.  
HTTP Status Code: 400

## See Also<a name="API_StartTranscriptionJob_SeeAlso"></a>

For more information about using this API in one of the language\-specific AWS SDKs, see the following:

+  [AWS Command Line Interface](http://docs.aws.amazon.com/goto/aws-cli/transcribe-2017-10-26/StartTranscriptionJob) 

+  [AWS SDK for \.NET](http://docs.aws.amazon.com/goto/DotNetSDKV3/transcribe-2017-10-26/StartTranscriptionJob) 

+  [AWS SDK for C\+\+](http://docs.aws.amazon.com/goto/SdkForCpp/transcribe-2017-10-26/StartTranscriptionJob) 

+  [AWS SDK for Go](http://docs.aws.amazon.com/goto/SdkForGoV1/transcribe-2017-10-26/StartTranscriptionJob) 

+  [AWS SDK for Java](http://docs.aws.amazon.com/goto/SdkForJava/transcribe-2017-10-26/StartTranscriptionJob) 

+  [AWS SDK for JavaScript](http://docs.aws.amazon.com/goto/AWSJavaScriptSDK/transcribe-2017-10-26/StartTranscriptionJob) 

+  [AWS SDK for PHP V3](http://docs.aws.amazon.com/goto/SdkForPHPV3/transcribe-2017-10-26/StartTranscriptionJob) 

+  [AWS SDK for Python](http://docs.aws.amazon.com/goto/boto3/transcribe-2017-10-26/StartTranscriptionJob) 

+  [AWS SDK for Ruby V2](http://docs.aws.amazon.com/goto/SdkForRubyV2/transcribe-2017-10-26/StartTranscriptionJob) 