{
    "title": "File service interface overview",
    "linkTitle": "File service interface overview",
    "weight": "210"
}For SecureTransport to receive a file using the file services interface, the external system must copy the file into the shared file system. The external system then sends the parameters for the transfer in the metadata file using another protocol.

To perform a file services interface transfer, the external server:

1.  Copies the file to transfer to a location in the shared folder.
2.  Construct a metadata file that specifies the parameters of the transfer.
3.  Upload the metadata file into the subscription folder of an application of type File Transfer via File Services Interface.

The SecureTransport Server:

1.  Reads the specification of the transfer from the metadata file.
2.  Copies the transferred file from the shared directory to the locations specified in the metadata file.
3.  Deletes the metadata file.
4.  Deletes the transferred file from the shared directory, if specified in the metadata file.

When SecureTransport sends a file using the file services interface, it calls a connector process configured by the developer which pushes the file to the remote server.
