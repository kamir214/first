hewwo dea ra di nn.
```lua
INVERTED = false

-- Get the image
IMAGE = love.image.newImageData("PIC.PNG")

if not IMAGE then
    error("IMAGE WASN'T LOADED!")
end

-- Create a table that will have ASCII characters
CHARS = {
    "A", --1
    "D", --2
    "V", --3
    "H", --4
    "X", --5
    "O", --6
    "1", --7
    "/", --8
    "?", --9
    ":", --10
    "}", --11
    "+", --12
    "-", --13
    "$", --14
    "#", --15
    "@", --16
    "!" --17
}

-- Table that will hold our ASCII art:
ROWS = {}

-- And finally, generate our ASCII art!
for a = 1, IMAGE:getHeight() do
    ROWS[a] = ""
    for b = 1, IMAGE:getWidth() do
        -- First, get the RGB values of the pixel
        R, G, B = IMAGE:getPixel(b - 1, a - 1)
        AVG = (R + G + B) / 3

        -- Calculate the index of the ASCII character
        CHAR_INDEX = math.floor((#CHARS - 1) * (AVG / 255) + 1)

        -- Get the ASCII character
        ASCII = CHARS[CHAR_INDEX]

        -- Add the ASCII character to the row
        ROWS[a] = ROWS[a] .. ASCII
    end
end

-- Print the ASCII art
for a = 1, #ROWS do
    print(ROWS[a])
end

-- Save the ASCII art to a file
FILENAME = 'IMAGE.TXT'
love.filesystem.remove(FILENAME)
file = love.filesystem.newFile(FILENAME)

for a = 1, #ROWS do
    file:open('a')
    file:write(ROWS[a] .. "\n")
    file:close()
end
```
