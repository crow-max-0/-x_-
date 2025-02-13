-- 클라이언트 스크립트
local Players = game:GetService("Players")
local UserInputService = game:GetService("UserInputService")
local LocalPlayer = Players.LocalPlayer

-- GUI 생성
local ScreenGui = Instance.new("ScreenGui", game.CoreGui)
local Hub = Instance.new("Frame", ScreenGui)
Hub.Size = UDim2.new(0.375, 0, 0.65, 0)
Hub.Position = UDim2.new(0.3125, 0, 0.35, 0)
Hub.BackgroundColor3 = Color3.new(0, 0, 0)
Hub.BackgroundTransparency = 0.5
Hub.Active = true
Hub.Draggable = true

-- 상단에 "콘솔x 허브" 텍스트 추가
local TitleLabel = Instance.new("TextLabel", Hub)
TitleLabel.Size = UDim2.new(1, 0, 0.1, 0)
TitleLabel.Position = UDim2.new(0, 0, 0, 0)
TitleLabel.Text = "콘솔x 허브"
TitleLabel.TextColor3 = Color3.new(1, 1, 1)
TitleLabel.BackgroundTransparency = 1
TitleLabel.Font = Enum.Font.SourceSans
TitleLabel.TextScaled = true
TitleLabel.TextSize = 14

-- Made by 콘솔x텍스트
local Label = Instance.new("TextLabel", Hub)
Label.Size = UDim2.new(1, 0, 0.1, 0)
Label.Position = UDim2.new(0, 0, 0.85, 0)
Label.Text = "Made by 콘솔x"
Label.TextColor3 = Color3.new(1, 1, 1)
Label.BackgroundTransparency = 1
Label.Font = Enum.Font.SourceSans
Label.TextScaled = true
Label.TextSize = 14

-- 버튼 생성 함수
local function createButton(parent, text, size, position, callback)
    local Button = Instance.new("TextButton", parent)
    Button.Size = size
    Button.Position = position
    Button.Text = text
    Button.TextColor3 = Color3.new(0, 0, 0)
    Button.BackgroundColor3 = Color3.new(1, 0, 0)
    Button.BorderSizePixel = 0
    Button.Font = Enum.Font.SourceSans
    Button.TextScaled = true
    Button.AutoButtonColor = false
    Button.BackgroundTransparency = 0

    -- 버튼 모서리를 둥글게 만들기
    local corner = Instance.new("UICorner")
    corner.CornerRadius = UDim.new(0.1, 0)
    corner.Parent = Button

    -- 버튼 클릭 이벤트 추가
    if callback then
        Button.MouseButton1Click:Connect(callback)
    end

    return Button
end

-- 버튼 생성
local button1 = createButton(Hub, "J의 허브", UDim2.new(0.25, 0, 0.2, 0), UDim2.new(0.125, 0, 0.1, 0), function()
    loadstring(game:HttpGet('https://raw.githubusercontent.com/Himynamefake/eqw/refs/heads/main/JayThePrime'))()
end)
local button2 = createButton(Hub, "힘찬이 허브", UDim2.new(0.25, 0, 0.2, 0), UDim2.new(0.625, 0, 0.1, 0), function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/himc573/himc573/refs/heads/main/%40%ED%9E%98%EC%B0%ACHUB-%ED%9E%98%EC%B0%AC%EC%9D%B4%EC%A0%9C%EC%9E%91"))()
end)
local button3 = createButton(Hub, "Ce핑", UDim2.new(0.25, 0, 0.2, 0), UDim2.new(0.125, 0, 0.4, 0), function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/Dain29292929/Ce1/refs/heads/main/Ce1"))()
end)
local button4 = createButton(Hub, "iwv", UDim2.new(0.25, 0, 0.2, 0), UDim2.new(0.625, 0, 0.4, 0), function()
    loadstring(game:HttpGet('https://raw.githubusercontent.com/pudong8452/test_case_h/main/Ray_Free'))()
end)
local button5 = createButton(Hub, "기존 5", UDim2.new(0.25, 0, 0.2, 0), UDim2.new(0.125, 0, 0.7, 0))
local button6 = createButton(Hub, "기존 6", UDim2.new(0.25, 0, 0.2, 0), UDim2.new(0.625, 0, 0.7, 0))

-- 허브 왼쪽에 ">" 버튼 생성
local toggleButton = createButton(Hub, ">", UDim2.new(0.1, 0, 0.1, 0), UDim2.new(0, 0, 0.45, 0))
local toggleState = false  -- 버튼 상태 변수

-- 버튼 클릭 시 동작
toggleButton.MouseButton1Click:Connect(function()
    toggleState = not toggleState  -- 상태 반전
    button1.Visible = not toggleState
    button2.Visible = not toggleState
    button3.Visible = not toggleState
    button4.Visible = not toggleState
    button5.Visible = not toggleState
    button6.Visible = not toggleState
    toggleButton.Text = toggleState and "<" or ">"
end)
