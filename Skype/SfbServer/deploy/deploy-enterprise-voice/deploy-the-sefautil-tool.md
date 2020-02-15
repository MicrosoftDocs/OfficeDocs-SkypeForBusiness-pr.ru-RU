---
title: Развертывание средства SEFAUtil в Skype для бизнеса
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
description: Развертывание средства SEFAUtil в Skype для бизнеса Server.
ms.openlocfilehash: 306e2ec305e9e12cd3486691b3e239e2aedfb548
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "41986814"
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business"></a><span data-ttu-id="76d7c-103">Развертывание средства SEFAUtil в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="76d7c-103">Deploy the SEFAUtil tool in Skype for Business</span></span>
 
<span data-ttu-id="76d7c-104">Развертывание средства SEFAUtil в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="76d7c-104">Deploying the SEFAUtil tool in Skype for Business Server.</span></span>
  
<span data-ttu-id="76d7c-105">Для развертывания и управления групповой отправке звонков необходимо использовать версию средства SEFAUtil для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="76d7c-105">To deploy and manage Group Call Pickup, you need to use the Skype for Business Server version of the SEFAUtil tool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="76d7c-106">Среда выполнения Microsoft Unified Communications Managed API (UCMA) 5 должна быть установлена на любой компьютер, на котором планируется запускать средство SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="76d7c-106">Microsoft Unified Communications Managed API (UCMA) 5 Runtime must be installed on any computer where you plan to run the SEFAUtil tool.</span></span> <span data-ttu-id="76d7c-107">Скачайте его здесь: [Managed Communications Managed API 5,0 Runtime](https://www.microsoft.com/download/details.aspx?id=47344).</span><span class="sxs-lookup"><span data-stu-id="76d7c-107">Download it here: [Unified Communications Managed API 5.0 Runtime](https://www.microsoft.com/download/details.aspx?id=47344).</span></span> <span data-ttu-id="76d7c-108">Кроме того, вы можете скачать пакет SDK UCMA 5, включающий среду выполнения, здесь: [UCMA 5,0 SDK](https://www.microsoft.com/download/details.aspx?id=47345).</span><span class="sxs-lookup"><span data-stu-id="76d7c-108">You can also download the UCMA 5 SDK, which includes the runtime, here: [UCMA 5.0 SDK](https://www.microsoft.com/download/details.aspx?id=47345).</span></span>
  
<span data-ttu-id="76d7c-109">Средство SEFAUtil можно использовать в любом пуле переднего плана в развертывании.</span><span class="sxs-lookup"><span data-stu-id="76d7c-109">You can run the SEFAUtil tool in any Front End pool in your deployment.</span></span> <span data-ttu-id="76d7c-110">Для запуска средства SEFAUtil необходимо выполнить действия 1, 2 и 3 в мастере развертывания Skype для бизнеса на доверенном компьютере приложения.</span><span class="sxs-lookup"><span data-stu-id="76d7c-110">To run the SEFAUtil tool you must run Steps 1, 2, and 3 from the Skype for Business Deployment Wizard on the Trusted Application Computer.</span></span> <span data-ttu-id="76d7c-111">Для SEFAUtil требуется, чтобы локальное хранилище конфигурации присутствовало, а также для сертификата.</span><span class="sxs-lookup"><span data-stu-id="76d7c-111">SEFAUtil requires the local configuration store to be present, as well as a certificate.</span></span>
  
> [!NOTE]
> <span data-ttu-id="76d7c-112">Дополнительные сведения о запуске SEFAUtil можно найти в статье блог "[как получить SEFAUtil?](https://go.microsoft.com/fwlink/?LinkId=278940)".</span><span class="sxs-lookup"><span data-stu-id="76d7c-112">For more details about running SEFAUtil, see the  blog article, "[How to get SEFAutil running?](https://go.microsoft.com/fwlink/?LinkId=278940)".</span></span> 
  
### <a name="to-deploy-sefautil"></a><span data-ttu-id="76d7c-113">Развертывание SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="76d7c-113">To deploy SEFAUtil</span></span>

1. <span data-ttu-id="76d7c-114">Выполните вход на компьютер, на котором установлена командная консоль Skype для бизнеса Server, в качестве члена группы RTCUniversalServerAdmins или с необходимыми правами пользователя, как описано в разделе **Делегирование разрешений на установку**.</span><span class="sxs-lookup"><span data-stu-id="76d7c-114">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="76d7c-115">Запустите консоль управления Skype для бизнеса Server: нажмите кнопку **Пуск**, последовательно выберите **все программы**, **Skype для бизнеса 2015**и щелкните **Командная консоль Skype для бизнеса Server**.</span><span class="sxs-lookup"><span data-stu-id="76d7c-115">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="76d7c-116">Средство SEFAUtil можно запускать только на компьютере, входящем в пул доверенных приложений.</span><span class="sxs-lookup"><span data-stu-id="76d7c-116">The SEFAUtil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="76d7c-117">При необходимости определите доверенный пул приложений для пула переднего плана, где планируется запускать SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="76d7c-117">If needed, define a trusted application pool for the Front End pool where you plan to run SEFAUtil.</span></span> <span data-ttu-id="76d7c-118">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="76d7c-118">At the command line, run:</span></span>
    
   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```
    > [!NOTE]
    > <span data-ttu-id="76d7c-119">Полное доменное имя пула: полное доменное имя сервера или пула, на котором будет размещаться приложение SEFAUtil (обычно это интерфейсный сервер или пул Skype для бизнеса).</span><span class="sxs-lookup"><span data-stu-id="76d7c-119">Pool FQDN: The FQDN of the server or pool that will host the SEFAUtil application (usually a Skype for Business Front End server or pool).</span></span>
    > <span data-ttu-id="76d7c-120">Полное доменное имя регистратора пула: полное доменное имя сервера или пула приложений Skype для бизнеса, связанных с этим пулом приложений.</span><span class="sxs-lookup"><span data-stu-id="76d7c-120">Pool Registrar FQDN: The FQDN of the Skype for Business Front End server or pool associated with this application pool.</span></span>
    > <span data-ttu-id="76d7c-121">Сайт пула: идентификатор сайта, на котором размещен этот пул.</span><span class="sxs-lookup"><span data-stu-id="76d7c-121">Pool Site: The Site ID of the site on which this pool is homed.</span></span>

4. <span data-ttu-id="76d7c-122">Определите средство SEFAUtil в качестве доверенного приложения.</span><span class="sxs-lookup"><span data-stu-id="76d7c-122">Define the SEFAUtil tool as a trusted application.</span></span> <span data-ttu-id="76d7c-123">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="76d7c-123">At the command line, run:</span></span>
    
   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
   ```

    > [!NOTE]
    > <span data-ttu-id="76d7c-124">При необходимости можно использовать другой порт.</span><span class="sxs-lookup"><span data-stu-id="76d7c-124">You can use a different port if needed.</span></span> 
  
5. <span data-ttu-id="76d7c-125">Включите топологию с изменениями.</span><span class="sxs-lookup"><span data-stu-id="76d7c-125">Enable the topology with your changes.</span></span> <span data-ttu-id="76d7c-126">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="76d7c-126">At the command line, run:</span></span>
    
   ```powershell
   Enable-CsTopology
   ```

6. <span data-ttu-id="76d7c-127">Если вы еще не сделали это, Скачайте версию средства SEFAUtil в Skype для бизнеса Server из [этого расположения](https://www.microsoft.com/download/details.aspx?id=52631)и установите ее в пул доверенных приложений, созданный на шаге 3.</span><span class="sxs-lookup"><span data-stu-id="76d7c-127">If you haven't already, download the Skype for Business Server version of the SEFAUtil tool from [this location](https://www.microsoft.com/download/details.aspx?id=52631), and install it on the trusted application pool you created in step 3.</span></span>
    
7. <span data-ttu-id="76d7c-128">Убедитесь, что средство SEFAUtil работает правильно, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="76d7c-128">Verify that the SEFAUtil tool is running correctly, as follows:</span></span> 
    
    <span data-ttu-id="76d7c-129">а.</span><span class="sxs-lookup"><span data-stu-id="76d7c-129">a.</span></span> <span data-ttu-id="76d7c-130">Запустите средство из командной строки Windows с правами администратора, чтобы отобразить параметры переадресации звонков пользователя в развертывании.</span><span class="sxs-lookup"><span data-stu-id="76d7c-130">Run the tool from the Windows command prompt with administrator privileges to display the call forwarding settings of a user in your deployment.</span></span>
    
    <span data-ttu-id="76d7c-131">б.</span><span class="sxs-lookup"><span data-stu-id="76d7c-131">b.</span></span> <span data-ttu-id="76d7c-132">Отображение параметров переадресации звонков пользователя.</span><span class="sxs-lookup"><span data-stu-id="76d7c-132">Display the call forwarding settings of a user.</span></span> <span data-ttu-id="76d7c-133">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="76d7c-133">At the command line, run:</span></span>
    
   ```console
   SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
   ```

<span data-ttu-id="76d7c-134">Будут отображены параметры переадресации звонков для пользователя.</span><span class="sxs-lookup"><span data-stu-id="76d7c-134">The call forwarding settings for the user will be displayed.</span></span>
    

