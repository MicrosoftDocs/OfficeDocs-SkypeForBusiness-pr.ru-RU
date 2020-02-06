---
title: Настройка политик для средства нагрузки и производительности Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 11/11/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7e1435e2-d073-4265-8067-ebcb5bf28835
description: Настройка политики для средства нагрузки и производительности Skype для Business Server 2015.
ms.openlocfilehash: bfdf0d9875a37f7f4a1f98aa24cd6fd5c3176a00
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816198"
---
# <a name="configuring-policies-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="b7145-103">Настройка политик для средства нагрузки и производительности Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="b7145-103">Configuring policies for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="b7145-104">Настройка политики для средства нагрузки и производительности Skype для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="b7145-104">Policy configuration for Skype for Business Server 2015 Stress and Performance Tool.</span></span>
  
<span data-ttu-id="b7145-105">Существует несколько политик и других областей, которые можно настроить в Skype для бизнеса Server 2015, прежде чем запускать средство "стресс и производительность".</span><span class="sxs-lookup"><span data-stu-id="b7145-105">There are several policies and other areas that you can configure in Skype for Business Server 2015, prior to running the Stress and Performance Tool:</span></span>
  
- <span data-ttu-id="b7145-106">[Политика архивации](configuring-policies.md#ArchivingPolicy),</span><span class="sxs-lookup"><span data-stu-id="b7145-106">[Archiving policy](configuring-policies.md#ArchivingPolicy)</span></span>
    
- <span data-ttu-id="b7145-107">[Политика конференц-связи](configuring-policies.md#ConferencingPolicy),</span><span class="sxs-lookup"><span data-stu-id="b7145-107">[Conferencing policy](configuring-policies.md#ConferencingPolicy)</span></span>
    
- [<span data-ttu-id="b7145-108">Политика контактов</span><span class="sxs-lookup"><span data-stu-id="b7145-108">Contacts policy</span></span>](configuring-policies.md#ContactsPolicy)
    
- [<span data-ttu-id="b7145-109">Политика Федерации</span><span class="sxs-lookup"><span data-stu-id="b7145-109">Federation policy</span></span>](configuring-policies.md#FederationPolicy)
    
- [<span data-ttu-id="b7145-110">Политика управления допуском звонков</span><span class="sxs-lookup"><span data-stu-id="b7145-110">Call Admission Control policy</span></span>](configuring-policies.md#CACPolicy)
    
- [<span data-ttu-id="b7145-111">Правила голосовой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="b7145-111">Voice Routing rules</span></span>](configuring-policies.md#VoiceRoutingRules)
    
- [<span data-ttu-id="b7145-112">Участие в программе конференции</span><span class="sxs-lookup"><span data-stu-id="b7145-112">Conference Attendant application</span></span>](configuring-policies.md#ConfAttendantApp)
    
- [<span data-ttu-id="b7145-113">Служба приостановки вызовов сервера</span><span class="sxs-lookup"><span data-stu-id="b7145-113">Server Call Park service</span></span>](configuring-policies.md#ServerCallParkServ)
    
- [<span data-ttu-id="b7145-114">Вызов экстренной помощи</span><span class="sxs-lookup"><span data-stu-id="b7145-114">Emergency calls</span></span>](configuring-policies.md#EmergencyCalls)
    
- [<span data-ttu-id="b7145-115">Настройка приложения группы ответа</span><span class="sxs-lookup"><span data-stu-id="b7145-115">Configuring Response Group application</span></span>](configuring-policies.md#ConfigResponseGroupApp)
    
## <a name="archiving-policy"></a><span data-ttu-id="b7145-116">Политика архивации</span><span class="sxs-lookup"><span data-stu-id="b7145-116">Archiving policy</span></span>
<span data-ttu-id="b7145-117"><a name="ArchivingPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="b7145-117"><a name="ArchivingPolicy"> </a></span></span>

<span data-ttu-id="b7145-118">Если у вас есть сервер архивации, развернутый в топологии сервера Skype для бизнеса, вы можете ознакомиться со сценарием Арчивингполици. ps1.</span><span class="sxs-lookup"><span data-stu-id="b7145-118">If you have an Archiving server deployed in your Skype for Business Server topology, you can look at the ArchivingPolicy.ps1 script.</span></span> <span data-ttu-id="b7145-119">Если вам нужна дополнительная помощь, ознакомьтесь с командлетами архивации и веб-конференций.</span><span class="sxs-lookup"><span data-stu-id="b7145-119">If you need further assistance, check out the Archiving and Web Conferencing cmdlets.</span></span>
  
## <a name="conferencing-policy"></a><span data-ttu-id="b7145-120">Политика конференц-связи</span><span class="sxs-lookup"><span data-stu-id="b7145-120">Conferencing policy</span></span>
<span data-ttu-id="b7145-121"><a name="ConferencingPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="b7145-121"><a name="ConferencingPolicy"> </a></span></span>

<span data-ttu-id="b7145-122">Для конференц-связи у нас есть сценарий Митингполици. ps1.</span><span class="sxs-lookup"><span data-stu-id="b7145-122">For conferencing, we have the MeetingPolicy.ps1 script.</span></span> <span data-ttu-id="b7145-123">Если вам нужна дополнительная помощь, ознакомьтесь с командлетами веб-конференций.</span><span class="sxs-lookup"><span data-stu-id="b7145-123">If you need further assistance, check out the Web Conferencing cmdlets.</span></span>
  
## <a name="contacts-policy"></a><span data-ttu-id="b7145-124">Политика контактов</span><span class="sxs-lookup"><span data-stu-id="b7145-124">Contacts policy</span></span>
<span data-ttu-id="b7145-125"><a name="ContactsPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="b7145-125"><a name="ContactsPolicy"> </a></span></span>

<span data-ttu-id="b7145-126">Контактсполици. ps1 — это пример, который вам нужно будет просмотреть.</span><span class="sxs-lookup"><span data-stu-id="b7145-126">ContactsPolicy.ps1 script will be the sample you'll need to review.</span></span> <span data-ttu-id="b7145-127">Командлеты для обмена мгновенными сообщениями и присутствия помогают вам в необходимости дальнейших ссылок.</span><span class="sxs-lookup"><span data-stu-id="b7145-127">The IM and Presence cmdlets will help if you need further references.</span></span>
  
## <a name="federation-policy"></a><span data-ttu-id="b7145-128">Политика Федерации</span><span class="sxs-lookup"><span data-stu-id="b7145-128">Federation policy</span></span>
<span data-ttu-id="b7145-129"><a name="FederationPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="b7145-129"><a name="FederationPolicy"> </a></span></span>

<span data-ttu-id="b7145-130">Пример сценария для Федерации — Федератионполици. ps1.</span><span class="sxs-lookup"><span data-stu-id="b7145-130">The sample script for federation is FederationPolicy.ps1.</span></span> <span data-ttu-id="b7145-131">Командлеты, которые нужно проверить, — пограничный сервер, Федерация и внешний доступ.</span><span class="sxs-lookup"><span data-stu-id="b7145-131">The cmdlets to review, if you need further insight, will be Edge Server, federation, and external access.</span></span>
  
## <a name="call-admission-control-policy"></a><span data-ttu-id="b7145-132">Политика управления допуском звонков</span><span class="sxs-lookup"><span data-stu-id="b7145-132">Call Admission Control policy</span></span>
<span data-ttu-id="b7145-133"><a name="CACPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="b7145-133"><a name="CACPolicy"> </a></span></span>

<span data-ttu-id="b7145-134">Вы можете добавить ссылку на Бандвидсполици. ps1 для этой политики.</span><span class="sxs-lookup"><span data-stu-id="b7145-134">You can reference BandwidthPolicy.ps1 for this policy.</span></span> <span data-ttu-id="b7145-135">Кроме того, у командлетов управления допуском звонков также будут дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="b7145-135">The Call Admission Control cmdlets will have further information as well.</span></span>
  
## <a name="voice-routing-rules"></a><span data-ttu-id="b7145-136">Правила голосовой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="b7145-136">Voice Routing rules</span></span>
<span data-ttu-id="b7145-137"><a name="VoiceRoutingRules"> </a></span><span class="sxs-lookup"><span data-stu-id="b7145-137"><a name="VoiceRoutingRules"> </a></span></span>

<span data-ttu-id="b7145-138">Для голосовой связи вам понадобится пример сценария Раутингрулес. ps1.</span><span class="sxs-lookup"><span data-stu-id="b7145-138">You'll need the RoutingRules.ps1 sample script for Voice Routing.</span></span> <span data-ttu-id="b7145-139">Когда вы настраиваете эти правила, запишите контекст телефона (то есть,/Локатион Profile или/Симпленаме), а также внутренние и внешние коды города, чтобы их можно было указывать при создании пользователей.</span><span class="sxs-lookup"><span data-stu-id="b7145-139">When you're configuring these rules, take note of the phone context (that is, /Location Profile or /SimpleName) and Internal/External Area Codes, so that you can specify them when creating users.</span></span> <span data-ttu-id="b7145-140">Они также понадобятся во время настройки Линкперфтул (специально для PSTN-UC и UC-КТСОП).</span><span class="sxs-lookup"><span data-stu-id="b7145-140">You'll also need them during LyncPerfTool configuration (specifically for PSTN-UC and UC-PSTN).</span></span>
  
<span data-ttu-id="b7145-141">Например, параметр Симпленаме в вызове командлета **New-ксдиалплан** в примере раутингрулес. ps1 следует использовать для значения локатионпрофиле на следующем рисунке файла усерпрофилеженератор. exe:</span><span class="sxs-lookup"><span data-stu-id="b7145-141">For example, the SimpleName parameter in the call to the **New-CsDialPlan** cmdlet in the RoutingRules.ps1 example should be used for the LocationProfile value in the following figure of UserProfileGenerator.exe:</span></span>
  
![Средство конфигурации нагрузки Skype для бизнеса, вкладка Voice Scenarios (Голосовые сценарии), дополнительные параметры для бесед.](../../media/59f42e4e-8f1e-4d43-9ae2-9e6026191951.png)
  
<span data-ttu-id="b7145-143">Подробнее вы можете просмотреть командлеты для корпоративных голосовых команд.</span><span class="sxs-lookup"><span data-stu-id="b7145-143">For details, you can review the Enterprise Voice cmdlets.</span></span>
  
## <a name="conference-attendant-application"></a><span data-ttu-id="b7145-144">Участие в программе конференции</span><span class="sxs-lookup"><span data-stu-id="b7145-144">Conference Attendant application</span></span>
<span data-ttu-id="b7145-145"><a name="ConfAttendantApp"> </a></span><span class="sxs-lookup"><span data-stu-id="b7145-145"><a name="ConfAttendantApp"> </a></span></span>

<span data-ttu-id="b7145-146">Сначала прочтите сценарий Конференцеаутоаттендантконфигуратион. ps1.</span><span class="sxs-lookup"><span data-stu-id="b7145-146">First review the ConferenceAutoAttendantConfiguration.ps1 script.</span></span> <span data-ttu-id="b7145-147">Вы захотите заметку КонференЦингаутоаттендант номера телефона (1121111111 по умолчанию), чтобы можно было ввести его в средство настройки Линкперфтул для создания конфигурации, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="b7145-147">You'll want to take note of the ConferencingAutoAttendant phone number (1121111111 by default), so that you can enter it into the LyncPerfTool configuration tool for configuration generation, as below:</span></span>
  
![Вкладка Voice Scenarios (Голосовые сценарии) с уровнем нагрузки конференц-связи и номером телефона.](../../media/a3ea5fc0-8b3d-4842-b809-f137f470dbdc.png)
  
<span data-ttu-id="b7145-149">Дополнительные сведения можно найти в командлетах конференций и конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="b7145-149">You'll find more details in the Conferencing and Dial-in Conferencing cmdlets.</span></span>
  
## <a name="server-call-park-service"></a><span data-ttu-id="b7145-150">Служба приостановки вызовов сервера</span><span class="sxs-lookup"><span data-stu-id="b7145-150">Server Call Park service</span></span>
<span data-ttu-id="b7145-151"><a name="ServerCallParkServ"> </a></span><span class="sxs-lookup"><span data-stu-id="b7145-151"><a name="ServerCallParkServ"> </a></span></span>

<span data-ttu-id="b7145-152">По умолчанию это значение отключено.</span><span class="sxs-lookup"><span data-stu-id="b7145-152">This is actually disabled by default.</span></span> <span data-ttu-id="b7145-153">Вы можете проверить образец сценария Каллпаркконфигуратион. ps1, если это необходимо.</span><span class="sxs-lookup"><span data-stu-id="b7145-153">You can review the CallParkConfiguration.ps1 sample script if you need to test this.</span></span> <span data-ttu-id="b7145-154">Кроме того, изучите командлеты приложения для приостановки вызова по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="b7145-154">Additionally, check out the Call Park Application cmdlets as needed.</span></span>
  
## <a name="emergency-calls"></a><span data-ttu-id="b7145-155">Вызов экстренной помощи</span><span class="sxs-lookup"><span data-stu-id="b7145-155">Emergency calls</span></span>
<span data-ttu-id="b7145-156"><a name="EmergencyCalls"> </a></span><span class="sxs-lookup"><span data-stu-id="b7145-156"><a name="EmergencyCalls"> </a></span></span>

<span data-ttu-id="b7145-157">Чтобы настроить стресс и тестирование производительности для экстренных вызовов, необходимо выполнить описанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="b7145-157">You'll need to perform the following steps to configure stress and performance testing for emergency calls:</span></span>
  
1. <span data-ttu-id="b7145-158">Настройте голосовой маршрут для вызова экстренной помощи.</span><span class="sxs-lookup"><span data-stu-id="b7145-158">Set up a voice route for emergency calls.</span></span> <span data-ttu-id="b7145-159">Вы можете использовать сценарий Раутингрулес. ps1 и прочтите раздел " **E911 Route to КТСОП** ", чтобы настроить этот голосовой маршрут.</span><span class="sxs-lookup"><span data-stu-id="b7145-159">You can use the RoutingRules.ps1 script, and check under the comment " **Route E911 to PSTN** " for an example of how to set up this voice route.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="b7145-160">Пример команды в Раутингрулес. ps1 имеет числовой шаблон, который включает число 119 вместо 911.</span><span class="sxs-lookup"><span data-stu-id="b7145-160">The example command in RoutingRules.ps1 has a number pattern that includes the number 119 rather than 911.</span></span> <span data-ttu-id="b7145-161">Следует избегать использования 911 (или фактического местного номера для экстренного реагирования), чтобы предотвратить случайные вызовы локальных аварийных операторов в ходе нагрузочного тестирования.</span><span class="sxs-lookup"><span data-stu-id="b7145-161">You should avoid using 911 (or your actual local emergency number) to prevent accidental calls to your local emergency operators during your load testing.</span></span> <span data-ttu-id="b7145-162">Помните, что эта конфигурация предназначена только для целей моделирования.</span><span class="sxs-lookup"><span data-stu-id="b7145-162">Remember, this configuration is for simulation purposes only!</span></span> 
  
2. <span data-ttu-id="b7145-163">Настройте адреса, заполнив значения на вкладке " **Настройка службы расположения** " в усерпровисионингтул, как показано на рисунке ниже.</span><span class="sxs-lookup"><span data-stu-id="b7145-163">Configure addresses by filling in the values on the **Location Info Service Config** tab in the UserProvisioningTool, as shown in the following figure:</span></span>
    
     ![Средство подготовки пользователей, отображающее количество адресов, подсетей, коммутаторов и портов.](../../media/ebe85a0c-750f-4301-97d4-d158a40ea98a.png)
  
3. <span data-ttu-id="b7145-165">После ввода всех данных в Усерпровисионингтул нажмите кнопку **создать файлы в файле LIS** .</span><span class="sxs-lookup"><span data-stu-id="b7145-165">When you've entered everything into the UserProvisioningTool, click the **Generate LIS Config Files** button.</span></span>
    
4. <span data-ttu-id="b7145-166">Теперь будут создаваться CSV-файлы для портов, подсетей, переключателей и точек доступа к беспроводной сети (Вапс), а также файла XML для инструмента "стресс и производительность".</span><span class="sxs-lookup"><span data-stu-id="b7145-166">Now CSV files for ports, subnets, switches, and wireless access points (WAPs), as well as an XML file for the Stress and Performance tool will be generated.</span></span> <span data-ttu-id="b7145-167">Вы можете использовать CSV-файлы для ввода при настройке службы сведений о расположении (LIS) с помощью сценария Лисконфигуратион. ps1.</span><span class="sxs-lookup"><span data-stu-id="b7145-167">You can use the CSV files for inputs when configuring the Location Information service (LIS) with the LisConfiguration.ps1 script.</span></span> <span data-ttu-id="b7145-168">Для этого вам потребуется переместить файл Locations0. XML в ту же папку, что и в средстве "стресс и производительность" (Линкперфтул. exe).</span><span class="sxs-lookup"><span data-stu-id="b7145-168">To do this, you'll need to move the Locations0.xml file to the same folder as the Stress and Performance Tool executable (LyncPerfTool.exe).</span></span> <span data-ttu-id="b7145-169">Это позволит вам запускать сценарии профилей местоположений (абонентские планы).</span><span class="sxs-lookup"><span data-stu-id="b7145-169">This will let you run location profile (dial plan) scenarios.</span></span>
    
## <a name="configuring-response-group-application"></a><span data-ttu-id="b7145-170">Настройка приложения группы ответа</span><span class="sxs-lookup"><span data-stu-id="b7145-170">Configuring Response Group application</span></span>
<span data-ttu-id="b7145-171"><a name="ConfigResponseGroupApp"> </a></span><span class="sxs-lookup"><span data-stu-id="b7145-171"><a name="ConfigResponseGroupApp"> </a></span></span>

<span data-ttu-id="b7145-172">Пример сценария — Респонсеграупконфигуратион. ps1.</span><span class="sxs-lookup"><span data-stu-id="b7145-172">The sample script is ResponseGroupConfiguration.ps1.</span></span> <span data-ttu-id="b7145-173">Кроме того, существуют командлеты приложения группы ответа для просмотра дополнительных сведений о конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b7145-173">There are also Response Group application cmdlets to review for further configuration details.</span></span> <span data-ttu-id="b7145-174">На следующей схеме показаны некоторые параметры конфигурации:</span><span class="sxs-lookup"><span data-stu-id="b7145-174">The following diagram will show some of the configuration details:</span></span>
  
![Средство конфигурации "Группа ответа" с существующими рабочими процессами для тестирования.](../../media/e218a345-4813-4332-8cff-b48de05017ef.jpg)
  

