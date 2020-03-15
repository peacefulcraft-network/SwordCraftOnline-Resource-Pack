# SwordCraftOnline-Resource-Pack
SwordCraftOnline Resource Pack

# Deployment
Any changes made to master trigger a pipeline to build the resource pack and push it to our webserver. The progress of builds can be tracked [here](https://github.com/peacefulcraft-network/SwordCraftOnline-Resource-Pack/actions) and the files will be uploaded [here](https://cdn.peacefulcraft.net/resources/) upon completion.

The server will not tell clients that there is a new version of the resource pack available until the `resource-pack-sha1` property in `server.properties` is changed. This value is also generated in the build process and is placed in the `hash.sha1` file with the resource pack at the above link. Just open the `.sha1` file, copy the hash out, and paste the new value into server config and restart. Note that the hash is just the first string, do not include the filename. IE: `ece3b3e0f4e12d98cba2ad6e0be19237293838b3`.

**Step By Step**
1. Merge / push changes to master
2. Wait for pipeline to [complete](https://github.com/peacefulcraft-network/SwordCraftOnline-Resource-Pack/actions)
3. The resource pack .zip file will be [here](https://cdn.peacefulcraft.net/resources/swordcraftonline_resource_pack.zip)
4. The sha1 hash will be [here](https://cdn.peacefulcraft.net/resources/hash.sha1)
5. To update the resource pack on a server, get the hash from the hash file linked in step 4 and paste it into the `resource-pack-sha1` field of the `server.properties` file. Example: `resource-pack-sha1=ece3b3e0f4e12d98cba2ad6e0be19237293838b3`.
6. Restart server
