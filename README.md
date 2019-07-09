# Roblox

Timer / Clock GUI Script 
Format: 00:00

--TimeInSeconds is input time value for seconds
-- test input value: 59, 60, 61

local TimeInSeconds = 59
local TimeInMinutes = math.floor(TimeInSeconds/60)
local reminder = TimeInSeconds%60
print (reminder)

local flag = false;

local clockText = script.Parent.Clock

if reminder ==0 then
	TimeInMinutes = TimeInMinutes -1;
	flag = true;
else
	flag = false;
end
print (flag)

for i = 1,reminder do
	wait(1) 
	if TimeInMinutes > 9 then
		if reminder -i <10 then
			clockText.Text = TimeInMinutes ..":0".. reminder -i
		else
			clockText.Text = TimeInMinutes ..":".. reminder -i
		end
	else
		if reminder -i <10 then
			clockText.Text = "0"..TimeInMinutes ..":0".. reminder -i
		else
			clockText.Text ="0".. TimeInMinutes ..":".. reminder -i
		end
	end
	print(clockText.Text)
end

if flag == false then
	TimeInMinutes = TimeInMinutes -1
	for i=0, TimeInMinutes do
		for i=1, 60 do
			wait(1)
			if TimeInMinutes > 9 then
				if 60 -i <10 then
					clockText.Text =TimeInMinutes ..":0".. (60 -i)
				else
					clockText.Text =TimeInMinutes ..":".. (60 -i)			
				end
			else
				if 60 -i <10 then
					clockText.Text ="0"..TimeInMinutes ..":0".. (60 -i)
				else
					clockText.Text ="0"..TimeInMinutes ..":".. (60 -i)			
				end
			end
		end
		if TimeInMinutes >=1 then
			TimeInMinutes = TimeInMinutes -1
		end	
	end
else
	for i=0, TimeInMinutes do
		for i=1, 60 do
			wait(1)
			if TimeInMinutes > 9 then
				if 60 -i <10 then
					clockText.Text =TimeInMinutes ..":0".. (60 -i)
				else
					clockText.Text =TimeInMinutes ..":".. (60 -i)			
				end
			else
				if 60 -i <10 then
					clockText.Text ="0"..TimeInMinutes ..":0".. (60 -i)
				else
					clockText.Text ="0"..TimeInMinutes ..":".. (60 -i)			
				end
			end
			print(i..":--"..clockText.Text)
		end
		if TimeInMinutes >=1 then
			TimeInMinutes = TimeInMinutes -1
		end			
	end
end

