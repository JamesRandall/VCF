# Build Your Own Adaptor (BYOA)
A collection of adaptors written by Mark Cooper to extend Videris.
* Gravatar
* Little Sis

## Configuration
To enable or disable searchers, update `config.yml` and set "enabled" as `True` or `False`.

```yaml 
    searchers:
      littlesis:        # <<< Note this must be identical to the id
        id: littlesis   
        name: Little Sis
        hint: Search for a person
        tooltip: Find Gravatar profile by email address
        enabled: True
```

## Adaptors
### Gravatar
Gravatar.com is a platform that allows users to reuse the same profile and avatar across a variety of different platforms - Wordpress being a significant participating platform.

This adaptor allows Videris users to search for the gravatar profiles by supplying the target's email address. If a matching profile is found, it is returned along with entities for each of the linked accounts and email addresses listed on the profile (Flickr, Facebook, Goodreads, Tumblr, Twitter, Wordpress).

### Little Sis
LittleSis.org is a free database of who-knows-who at the heights of business and government. It seems to be quite US-centric but holds a large network, connecting the dots between the world's most powerful people and organizations. 

This adaptor allows Videris users to search for people or organisations by name. Results will be returned for each match along with the relevant entities representing the person or organisation and their website (if available).

## Enabling the adaptors
The adaptors are written in Python 3.10 and make use of the FastAPI framework which runs on a uvicorn server. 

Install the required packages:

    pip install -r requirements.txt
    
Run API on the uvicorn server:

    uvicorn main:app --host <IPv4 address>
    
The IPv4 ip address needs to be accessible to Videris so make sure you configure any necessary port forwarding rules.
    
