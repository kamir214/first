# ! this repo is meant to be a dump. <ins>do not</ins> complain.

hewwo dea ra di nn.
```lua
INVERTED=false IMAGE=love.image.newImageData("input.png") if not IMAGE then error("IMAGE WASN'T LOADED!")end CHARS={"A","V","H","X","O","1","/","?",":","}","+","-","$","#","!"}ROWS={}for a=1,IMAGE:getHeight()do ROWS[a]=""for b=1,IMAGE:getWidth()do R,G,B=IMAGE:getPixel(b-1,a-1)AVG=(R+G+B)/3 CHAR_INDEX=math.floor((#CHARS-1)*(AVG/255)+1)ASCII=CHARS[CHAR_INDEX]ROWS[a]=ROWS[a]..ASCII end end for a=1,#ROWS do print(ROWS[a])end FILENAME = 'ASCII.txt'love.filesystem.remove(FILENAME)file=love.filesystem.newFile(FILENAME)for a=1,#ROWS dofile:open('a')file:write(ROWS[a].."\n")file:close()end
```
# bye. whatever you are doing here. go play <a href="https://youwilldie.neocities.org/test">ghoul3remake.wad</a>
![image](https://youwilldie.neocities.org/data.png)
