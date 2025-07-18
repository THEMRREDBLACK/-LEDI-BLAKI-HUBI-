-- VERSÃO PRA EU

local OrionLib = loadstring(game:HttpGet(('https://raw.githubusercontent.com/Kiwilegazin/Orion-mobile-v2/refs/heads/main/README.md')))()



-- LA ELE RECEBA CASCA DE BALA 

local Window = OrionLib:MakeWindow({

    Name = "🎩RED BLACK HUB-BROOCKHAVEN🎩",

    HidePremium = false,

    SaveConfig = true,

    ConfigFolder = "OrionTest",

    IntroEnabled = false

})


local args = {
    [1] = "RolePlayName",
    [2] = "🎩THE MR RED BLACK OWNER🎩"
}

game:GetService("ReplicatedStorage"):WaitForChild("RE"):WaitForChild("1RPNam1eTex1t"):FireServer(unpack(args))

-- NOSAAA

local Tab1 = Window:MakeTab({

    Name = "👨‍💻SCRIPTS👨‍💻",

    Icon = "rbxassetid://87117402316439",

    PremiumOnly = false

})



-- AI MEU CU

Tab1:AddTextbox({

    Name = "🤑COLOCA A MERDA DO SCRIPT LOGO🤑",

    Default = "",

    TextDisappear = false,

    Callback = function(text)

        _G.scriptCode = text

    end

})



-- BRUH

Tab1:AddButton({

    Name = "📄EXECUTAR O SCRIPT QUE TU COLOCOU NA MERDA DA TEXT BOX📄",

    Callback = function()

        if _G.scriptCode and _G.scriptCode ~= "" then

            local func = loadstring(_G.scriptCode)

            if func then

                func()

            else

                print("Erro ao carregar o script.")

            end

        else

            print("Por favor, insira um script válido na TextBox.")

        end

    end

})



-- SCRIPTS FICA NESSE CARALHO



Tab1:AddButton({

    Name = "🤑ESP RED BLACK🤑",

    Callback = function()

        loadstring(game:HttpGet('https://rawscripts.net/raw/Universal-Script-ESP-VERIFICADOR-DE-PLAYERS-V5-27937'))()

    end

})



Tab1:AddButton({
    Name = "🇧🇷CLEITIN HUB V4🇧🇷",
    Callback = function()
loadstring(game:HttpGet("https://raw.githubusercontent.com/CLEITI6966/Brookhaven/refs/heads/main/start.lua"))()
    end
})

Tab1:AddButton({

    Name = "🕹️SANDER X🕹️",

    Callback = function()

        loadstring(game:HttpGet('https://rawscripts.net/raw/Brookhaven-RP-Sander-X-Hub-Latest-Version-3-16718'))()

    end

})



Tab1:AddButton({

    Name = "✈️FLY GUI✈️",

    Callback = function()

        loadstring(game:HttpGet("https://rawscripts.net/raw/Brookhaven-andx1F3E1RP-Fly-Gui-15924"))()

    end

})



Tab1:AddButton({

    Name = "💰WALK FLING(SOMENTE EM MAPAS COM COLISÃO DE PLAYERS)💰",

    Callback = function()

       loadstring(game:HttpGet("https://rawscripts.net/raw/Universal-Script-Walk-Fling-Script-18573"))()

    end

})


Tab1:AddButton({
    Name = "☄️R4D SEM KEY☄️",
    Callback = function()
        loadstring(game:HttpGet("https://rawscripts.net/raw/Brookhaven-RP-R4D-script-no-key-17562"))()
  end
})

Tab1:AddButton({

    Name = "📄INFINITE YIELD📄",

    Callback = function()

    loadstring(game:HttpGet("https://rawscripts.net/raw/Infinite-Yield_500"))()

    end

})



Tab1:AddButton({

    Name = "🌐TROLL GUI🌐",

    Callback = function()

        loadstring(game:HttpGet("https://rawscripts.net/raw/Universal-Script-Troll-Gui-3874"))()

    end

})



-- PEGA NO MEU PAL

local Tab2 = Window:MakeTab({

    Name = "🥳TOOLS/LAG SERVER🥳",

    Icon = "rbxassetid://85371650668851",

    PremiumOnly = false

})



Tab2:AddButton({

    Name = "🍖Equipar Todos os Itens🍖",

    Callback = function()

        equipAllItems()

    end

})

Tab2:AddButton({

    Name = "👨‍🔬TELEPORT TOOL👨‍🔬",

    Callback = function()

        loadstring(game:HttpGet("https://rawscripts.net/raw/Universal-Script-Teleport-Tool-27419"))()

    end

})



Tab2:AddButton({

    Name = "🤑TELEKINIS🤑",

    Callback = function()

        loadstring(game:HttpGet("https://rawscripts.net/raw/Universal-Script-Fe-Telekinesis-V5-21542"))()

    end

})



-- Função para teletransportar o jogador para uma posição e depois voltar
function teleporteEVoltar()
    local player = game.Players.LocalPlayer
    if player and player.Character and player.Character:FindFirstChild("HumanoidRootPart") then
        -- Salva a posição original
        local posicaoOriginal = player.Character.HumanoidRootPart.CFrame

        -- Teletransporta para a posição especificada
        local novaPosicao = CFrame.new(-58, -28, 113)
        player.Character.HumanoidRootPart.CFrame = novaPosicao
        print("Teletransportado para a nova posição: " .. tostring(novaPosicao))

        -- Espera 5 segundos antes de retornar
        wait(5)

        -- Retorna à posição original
        player.Character.HumanoidRootPart.CFrame = posicaoOriginal
        print("Retornou à posição original: " .. tostring(posicaoOriginal))
    else
        print("Não foi possível teletransportar o jogador.")
    end
end

-- Adiciona o botão "☄️ MÃO DE FOGO☄️" na aba desejada
Tab2:AddButton({
    Name = "☄️ MÃO DE FOGO☄️",
    Callback = function()
        teleporteEVoltar()
    end
})

local Tab3 = Window:MakeTab({

    Name = "🤣TROLL🤣",

    Icon = "rbxassetid://127552583822854",

    PremiumOnly = false

})



-- Adiciona a caixa de texto persistente na aba "TROLL"
local playerName = ""

local TextBox = Tab3:AddTextbox({
    Name = "Nome do Jogador",
    Default = "",
    TextDisappear = false,
    Callback = function(value)
        playerName = value
        print("Nome do jogador inserido: " .. playerName)
    end
})

-- Botão "🤤VIEW PLAYER🤤"
Tab3:AddButton({
    Name = "🤤VIEW PLAYER🤤",
    Callback = function()
        local players = game:GetService("Players")
        for _, player in pairs(players:GetPlayers()) do
            if string.match(player.Name:lower(), playerName:lower()) or string.match(player.DisplayName:lower(), playerName:lower()) then
                print("Visualizando jogador: " .. player.Name)
                -- Adicione aqui o código para visualizar o jogador (ex: gui, highlight, etc.)
                break
            end
        end
    end
})

-- Botão "🤣TELEPORTE PLAYER🤣"
Tab3:AddButton({
    Name = "🤣TELEPORTE PLAYER🤣",
    Callback = function()
        local players = game:GetService("Players")
        local localPlayer = players.LocalPlayer
        for _, player in pairs(players:GetPlayers()) do
            if string.match(player.Name:lower(), playerName:lower()) or string.match(player.DisplayName:lower(), playerName:lower()) then
                if localPlayer and localPlayer.Character and localPlayer.Character:FindFirstChild("HumanoidRootPart") then
                    localPlayer.Character.HumanoidRootPart.CFrame = player.Character.HumanoidRootPart.CFrame
                    print("Teleportado para o jogador: " .. player.Name)
                end
                break
            end
        end
    end
})

Tab3:AddButton({

    Name = "🥵FLING RED BLACK🥵",

    Callback = function()

        loadstring(game:HttpGet('https://raw.githubusercontent.com/kiwi541/Mr-red-Black-V4/refs/heads/main/README.md'))()

    end

})



Tab3:AddButton({

    Name = "🤑PEGAR SOFÁ🤑",

    Callback = function()

        local player = game.Players.LocalPlayer

        if player and player.Character and player.Character:FindFirstChild("HumanoidRootPart") then

            player.Character.HumanoidRootPart.CFrame = CFrame.new(-82, 19, -130)

            print("Teletransportado para as coordenadas: X: -82, Y: 19, Z: -130")

        else

            print("Não foi possível teletransportar.")

        end

    end

})



local Tab4 = Window:MakeTab({

    Name = "😈TROLL VERSION V3😈",

    Icon = "rbxassetid://115893843340429",

    PremiumOnly = false

})



Tab4:AddButton({
    Name = "",
    Callback = function()

    end
})

Tab4:AddButton({
    Name = "😹TROLL VERSION BETA😹️",
    Callback = function()
    loadstring(game:HttpGet('https://redblackhub-protected.vercel.app/script'))()
    end
    })

Tab4:AddButton({
    Name = "🤑RED BLACK HUB BY VOLTZ🤑️",
    Callback = function()
        loadstring(game:HttpGet("https://raw.githubusercontent.com/ygagga/Red-Black-hub-1.0-/refs/heads/main/673b292c795c6275.txt"))()
        end
        })

Tab4:AddLabel("DESCULPA AI POR NÃO SABER CRIAR HUB BOM")
Tab4:AddLabel("MAS PRETENDO MELHORAR")
local Tab5 = Window:MakeTab({

    Name = "💀EXIBIÇÕES/REJOIN💀",

    Icon = "rbxassetid://92600174218873",

    PremiumOnly = false

})



Tab5:AddButton({

    Name = "⚠️REJOIN⚠️",

    Callback = function()

        game:GetService("TeleportService"):Teleport(game.PlaceId, game.Players.LocalPlayer)

    end

})



Tab5:AddButton({

    Name = "🌐COORDENADAS🌐",

    Callback = function()

        local player = game.Players.LocalPlayer

        if player and player.Character and player.Character:FindFirstChild("HumanoidRootPart") then

            local pos = player.Character.HumanoidRootPart.Position

            setclipboard(string.format("X: %d, Y: %d, Z: %d", pos.X, pos.Y, pos.Z))

            print("Coordenadas copiadas para a área de transferência: ", pos)

        else

            print("Não foi possível obter as coordenadas.")

        end

    end

})



local showModels = true



-- Função para enviar notificações de entrada e saída
function notificacaoEntradaSaida()
    local players = game:GetService("Players")

    -- Notificação de entrada
    players.PlayerAdded:Connect(function(player)
        local message = player.Name .. " entrou no jogo."
        game:GetService("StarterGui"):SetCore("ChatMakeSystemMessage", {
            Text = "🤑 " .. message .. " 🤑",
            Color = Color3.fromRGB(0, 255, 0), -- Verde para entrada
            Font = Enum.Font.SourceSansBold,
            TextSize = 18,
        })
        print(message)
    end)

    -- Notificação de saída
    players.PlayerRemoving:Connect(function(player)
        local message = player.Name .. " saiu do jogo."
        game:GetService("StarterGui"):SetCore("ChatMakeSystemMessage", {
            Text = "🤑 " .. message .. " 🤑",
            Color = Color3.fromRGB(255, 0, 0), -- Vermelho para saída
            Font = Enum.Font.SourceSansBold,
            TextSize = 18,
        })
        print(message)
    end)
end

-- Adiciona o botão "🤑 NOTIFICAÇÃO DE SAÍDA E ENTRADA🤑" na aba desejada
Tab5:AddButton({
    Name = "🤑 NOTIFICAÇÃO DE SAÍDA E ENTRADA🤑",
    Callback = function()
        notificacaoEntradaSaida()
    end
})

-- Função para evitar ser kickado por inatividade (Anti AFK)
function antiAFK()
    local player = game.Players.LocalPlayer
    local character = player.Character or player.CharacterAdded:Wait()
    local humanoidRootPart = character:WaitForChild("HumanoidRootPart")

    -- Função para mover o jogador periodicamente
    local function moverJogador()
        humanoidRootPart.CFrame = humanoidRootPart.CFrame * CFrame.new(0, 0, 0.1)
        wait(1)
        humanoidRootPart.CFrame = humanoidRootPart.CFrame * CFrame.new(0, 0, -0.1)
    end

    -- Loop para mover o jogador a cada 10 minutos (600 segundos)
    while true do
        wait(600) -- 10 minutos
        moverJogador()
    end
end

-- Adiciona o botão "🥶ANTI AFK🥶" na aba desejada
Tab5:AddButton({
    Name = "🥶ANTI AFK🥶",
    Callback = function()
        antiAFK()
    end
})


local Tab6 = Window:MakeTab({

    Name = "🧠CORPO🧠",

    Icon = "rbxassetid://120801516384560",

    PremiumOnly = false

})



local spinning = false



Tab6:AddButton({

    Name = "🌀Ativar Spin🌀",

    Callback = function()

        spinning = true

        while spinning do

            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame * CFrame.Angles(0, math.rad(10), 0)

            wait(0.1)

        end

        print("Spin ativado")

    end

})



Tab6:AddButton({

    Name = "💣Desativar Spin💣",

    Callback = function()

        spinning = false

        print("Spin desativado")

    end

})



local speed = 16

local jumpPower = 50



Tab6:AddTextbox({

    Name = "Velocidade",

    Default = tostring(speed),

    TextDisappear = false,

    Callback = function(text)

        local newSpeed = tonumber(text)

        if newSpeed then

            speed = newSpeed

            game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = speed

            print("Velocidade alterada para: " .. speed)

        else

            print("Por favor, insira um valor numérico válido para a velocidade.")

        end

    end

})



-- Botão Anti Sit

Tab6:AddButton({

    Name = "🪑ANTI SIT🪑",

    Callback = function()

        local humanoid = game.Players.LocalPlayer.Character:FindFirstChildOfClass("Humanoid")

        if humanoid then

            humanoid.Sit = false

            humanoid.Changed:Connect(function(property)

                if property == "Sit" then

                    humanoid.Sit = false

                end

            end)

            print("Anti Sit ativado")

        end

    end

})



-- Botão para voltar a conseguir sentar

Tab6:AddButton({

    Name = "🪑VOLTAR A CONSEGUIR SENTAR🪑",

    Callback = function()

        local humanoid = game.Players.LocalPlayer.Character:FindFirstChildOfClass("Humanoid")

        if humanoid then

            humanoid.Changed:Connect(function() end) -- Para remover o bloqueio de sentar

            print("Agora você pode sentar novamente")

        end

    end

})



Tab6:AddTextbox({

    Name = "Pulo",

    Default = tostring(jumpPower),

    TextDisappear = false,

    Callback = function(text)

        local newJumpPower = tonumber(text)

        if newJumpPower then

            jumpPower = newJumpPower

            game.Players.LocalPlayer.Character.Humanoid.JumpPower = jumpPower

            print("Pulo alterado para: " .. jumpPower)

        else

            print("Por favor, insira um valor numérico válido para o pulo.")

        end

    end

})



function equipAllItems()

    local character = game.Players.LocalPlayer.Character

    if character and character:FindFirstChildOfClass("Humanoid") then

        local humanoid = character:FindFirstChildOfClass("Humanoid")

        for i, tool in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do

            if tool:IsA("Tool") then

                humanoid:EquipTool(tool)

                print("Item equipado: " .. tool.Name)

            end

        end

    else

        print("Personagem não encontrado ou não possui um Humanoid.")

    end

end



local Tab7 = Window:MakeTab({

    Name = "🤳TIK TOK🤳",

    Icon = "rbxassetid://77458568185817",

    PremiumOnly = false

})



Tab7:AddButton({

    Name = "👨‍💻TIK TOK DO MR RED BLACK👨‍💻",

    Callback = function()

        setclipboard("THE_MR_RED_BLACK_OFC")

    end

})



Tab7:AddButton({

    Name = "🤪POLICE BROOKHAVEN OFC🤪",

    Callback = function()

        setclipboard("policebrookhavenofficial")

    end

})



Tab7:AddButton({

    Name = "👨‍💻MR POLICE👨‍💻",

    Callback = function()

        setclipboard("policebrookhaven99")

    end

})



local Tab8 = Window:MakeTab({

    Name = "👨‍💻OWNER SCRIPT👨‍💻",

    Icon = "rbxassetid://133887216434541",

    PremiumOnly = false

})



Tab8:AddLabel("🎩THE MR RED BLACK SCRIPTS OWNER🎩")
Tab8:AddLabel("💀MOLENGA COM CASPA💀")
Tab8:AddLabel("🥵MR POLICE🥵")

Tab8:AddLabel("👨‍🔬SR NESCAU👨‍🔬")

Tab8:AddLabel("👨‍💻FRAGIOTA👨‍💻")

Tab8:AddLabel("🤯RYAN🤯")
Tab8:AddLabel("🤖CHAT GPT🤖")


local Tab9 = Window:MakeTab({

    Name = "👕AVATAR👕️",

    Icon = "rbxassetid://112208414782742",

    PremiumOnly = false

})



-- Adiciona o botão "🤑SALVADOR DO BROOCKHAVEN NAME🤑" na aba desejada
Tab9:AddButton({
    Name = "🤑SALVADOR DO BROOCKHAVEN NAME🤑️",
    Callback = function()
        local args = {
            [1] = "RolePlayName",
            [2] = "🎩SALVADOR DO BROOCKHAVEN🎩"
        }

        game:GetService("ReplicatedStorage"):WaitForChild("RE"):WaitForChild("1RPNam1eTex1t"):FireServer(unpack(args))
        print("Nome de RP definido: 🎩SALVADOR DO BROOCKHAVEN🎩")
    end
})

-- Adiciona o botão "🕶️DEFINIR NOME DE RP (MEMBER)🕶️" na aba desejada
Tab9:AddButton({
    Name = "🕶️NOME DE RP RED BLACK MEMBER🕶️",
    Callback = function()
        local args = {
            [1] = "RolePlayName",
            [2] = "🎩RED BLACK MEMBER🎩"
        }

        game:GetService("ReplicatedStorage"):WaitForChild("RE"):WaitForChild("1RPNam1eTex1t"):FireServer(unpack(args))
        print("Nome de RP definido: 🎩RED BLACK MEMBER🎩")
    end
})

local TabChat = Window:MakeTab({

    Name = "💬CHAT💬",

    Icon = "rbxassetid://126878062099997",

    PremiumOnly = false

})



TabChat:AddButton({

    Name = "💬CHAT BY PASS💬",

    Callback = function()

        -- Executa o script fornecido

        loadstring(game:HttpGet('https://raw.githubusercontent.com/Gazer-Ha/bruh/refs/heads/main/ImBadd1'))()

        print("Script do tutorial executado")

    end

})



TabChat:AddButton({

    Name = "💬PLACA GIGANTE 1💬",

    Callback = function()

        local player = game.Players.LocalPlayer

        if player and player.Character and player.Character:FindFirstChild("HumanoidRootPart") then

            player.Character.HumanoidRootPart.CFrame = CFrame.new(-238, 88, -549)

            print("Teletransportado para as coordenadas: X: -238, Y: 88, Z: -549")

        else

            print("Não foi possível teletransportar.")

        end

    end

})



TabChat:AddButton({

    Name = "💬PLACA GIGANTE 2💬",

    Callback = function()

        local player = game.Players.LocalPlayer

        if player and player.Character and player.Character:FindFirstChild("HumanoidRootPart") then

            player.Character.HumanoidRootPart.CFrame = CFrame.new(443, 63, 513)

            print("Teletransportado para as coordenadas: X: 443, Y: 63, Z: 513")

        else

            print("Não foi possível teletransportar.")

        end

    end

})



TabChat:AddButton({

    Name = "💬PLACA GIGANTE 3💬",

    Callback = function()

        local player = game.Players.LocalPlayer

        if player and player.Character and player.Character:FindFirstChild("HumanoidRootPart") then

            player.Character.HumanoidRootPart.CFrame = CFrame.new(-633, 25, 361)

            print("Teletransportado para as coordenadas: X: -633, Y: 25, Z: 361")

        else

            print("Não foi possível teletransportar.")

        end

    end

})



-- Função para copiar texto para a área de transferência
function copiarTextoParaClipboard()
    local textoDeRaid = "🎩RAID RED BLACK🎩" -- Substitua pelo texto de raid desejado
    setclipboard(textoDeRaid)
    print("Texto copiado para a área de transferência.")
end

-- Adiciona o botão "💭COPIAR TEXTO DE RAID PARA A PLACA GIGANTE💭"
TabChat:AddButton({
    Name = "💭COPIAR TEXTO DE RAID PARA A PLACA GIGANTE💭",
    Callback = function()
        copiarTextoParaClipboard()
    end
})

-- Função para copiar texto para a área de transferência
function copiarTextoParaClipboard()
    local textoDeRaid = "☄️POLICE BROOCKHAVEN☄️" -- Substitua pelo texto de raid desejado
    setclipboard(textoDeRaid)
    print("Texto copiado para a área de transferência.")
end

-- Adiciona o botão "💭COPIAR TEXTO DE RAID PARA A PLACA GIGANTE💭"
TabChat:AddButton({
    Name = "💭COPIAR TEXTO DE RAID PARA A PLACA GIGANTE💭",
    Callback = function()
        copiarTextoParaClipboard()
    end
})

-- Função para copiar texto para a área de transferência
function copiarTextoParaClipboard()
    local textoDeRaid = "🇧🇷RAID ANTI TOXICS🇧🇷" -- Substitua pelo texto de raid desejado
    setclipboard(textoDeRaid)
    print("Texto copiado para a área de transferência.")
end

-- Adiciona o botão "💭COPIAR TEXTO DE RAID PARA A PLACA GIGANTE💭"
TabChat:AddButton({
    Name = "💭COPIAR TEXTO DE RAID PARA A PLACA GIGANTE💭",
    Callback = function()
        copiarTextoParaClipboard()
    end
})

local TabCasas = Window:MakeTab({
    Name = "🏠CASAS🏠",
    Icon = "rbxassetid://79352985337950",
    PremiumOnly = false
})

local TabTps = Window:MakeTab({
    Name = "☄️TELEPORTS☄️",
    Icon = "rbxassetid://124724023971625",
    PremiumOnly = false
})
