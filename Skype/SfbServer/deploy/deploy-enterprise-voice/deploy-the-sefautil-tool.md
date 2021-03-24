---
title: Развертывание средства SEFAUtil в Skype для бизнеса
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: 013890e3b65dfd3a8360da859a1c9179fa9b5a13
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51105805"
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business"></a><span data-ttu-id="a3a23-103">Развертывание средства SEFAUtil в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="a3a23-103">Deploy the SEFAUtil tool in Skype for Business</span></span>
 
<span data-ttu-id="a3a23-104">Развертывание средства SEFAUtil в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="a3a23-104">Deploying the SEFAUtil tool in Skype for Business Server.</span></span>
  
<span data-ttu-id="a3a23-105">Чтобы развернуть и управлять групповым вызовом, необходимо использовать версию Skype для бизнеса Server средства SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="a3a23-105">To deploy and manage Group Call Pickup, you need to use the Skype for Business Server version of the SEFAUtil tool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="a3a23-106">Microsoft Unified Communications Managed API (UCMA) 5 Runtime должен быть установлен на любом компьютере, на котором планируется запустить средство SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="a3a23-106">Microsoft Unified Communications Managed API (UCMA) 5 Runtime must be installed on any computer where you plan to run the SEFAUtil tool.</span></span> <span data-ttu-id="a3a23-107">Скачайте его здесь: [Управляемый API единой связи 5.0 Время запуска](https://www.microsoft.com/download/details.aspx?id=47344).</span><span class="sxs-lookup"><span data-stu-id="a3a23-107">Download it here: [Unified Communications Managed API 5.0 Runtime](https://www.microsoft.com/download/details.aspx?id=47344).</span></span> <span data-ttu-id="a3a23-108">Вы также можете скачать SDK UCMA 5, который включает время запуска, здесь: [UCMA 5.0 SDK](https://www.microsoft.com/download/details.aspx?id=47345).</span><span class="sxs-lookup"><span data-stu-id="a3a23-108">You can also download the UCMA 5 SDK, which includes the runtime, here: [UCMA 5.0 SDK](https://www.microsoft.com/download/details.aspx?id=47345).</span></span>
  
<span data-ttu-id="a3a23-109">Вы можете запустить средство SEFAUtil в любом пуле переднего конца в развертывании.</span><span class="sxs-lookup"><span data-stu-id="a3a23-109">You can run the SEFAUtil tool in any Front End pool in your deployment.</span></span> <span data-ttu-id="a3a23-110">Чтобы запустить средство SEFAUtil, необходимо выполнить этапы 1, 2 и 3 из мастера развертывания Skype для бизнеса на надежном компьютере приложения.</span><span class="sxs-lookup"><span data-stu-id="a3a23-110">To run the SEFAUtil tool you must run Steps 1, 2, and 3 from the Skype for Business Deployment Wizard on the Trusted Application Computer.</span></span> <span data-ttu-id="a3a23-111">ДЛЯ SEFAUtil требуется локальное хранилище конфигурации, а также сертификат.</span><span class="sxs-lookup"><span data-stu-id="a3a23-111">SEFAUtil requires the local configuration store to be present, as well as a certificate.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a3a23-112">Дополнительные сведения о запуске SEFAUtil см. в статье в блоге " Как получить[запуск SEFAutil?](/archive/blogs/jenstr/how-to-get-sefautil-running)".</span><span class="sxs-lookup"><span data-stu-id="a3a23-112">For more details about running SEFAUtil, see the  blog article, "[How to get SEFAutil running?](/archive/blogs/jenstr/how-to-get-sefautil-running)".</span></span> 
  
### <a name="to-deploy-sefautil"></a><span data-ttu-id="a3a23-113">Развертывание SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="a3a23-113">To deploy SEFAUtil</span></span>

1. <span data-ttu-id="a3a23-114">Войдите на компьютер, на котором установлена оболочка управления Skype для бизнес-серверов в качестве члена группы RTCUniversalServerAdmins или с необходимыми правами пользователя, как описано в разрешениях делегирования **установки.**</span><span class="sxs-lookup"><span data-stu-id="a3a23-114">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="a3a23-115">Запустите оболочку управления Skype для бизнес-серверов: нажмите кнопку Начните, щелкните Все **программы,** щелкните Skype для бизнеса **2015,** а затем нажмите **кнопку Skype для управления бизнес-серверами.**</span><span class="sxs-lookup"><span data-stu-id="a3a23-115">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="a3a23-116">Средство SEFAUtil можно запускать только на компьютере, который является частью доверенного пула приложений.</span><span class="sxs-lookup"><span data-stu-id="a3a23-116">The SEFAUtil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="a3a23-117">При необходимости определите доверенный пул приложений для пула переднего плана, в котором планируется запустить SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="a3a23-117">If needed, define a trusted application pool for the Front End pool where you plan to run SEFAUtil.</span></span> <span data-ttu-id="a3a23-118">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="a3a23-118">At the command line, run:</span></span>
    
   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```
    > [!NOTE]
    > <span data-ttu-id="a3a23-119">FQDN пула: FQDN сервера или пула, который будет принимать приложение SEFAUtil (обычно сервер или пул Skype для бизнеса).</span><span class="sxs-lookup"><span data-stu-id="a3a23-119">Pool FQDN: The FQDN of the server or pool that will host the SEFAUtil application (usually a Skype for Business Front End server or pool).</span></span>
    > <span data-ttu-id="a3a23-120">FQDN регистратора пула: FQDN переднего сервера Skype для бизнеса или пула, связанных с этим пулом приложений.</span><span class="sxs-lookup"><span data-stu-id="a3a23-120">Pool Registrar FQDN: The FQDN of the Skype for Business Front End server or pool associated with this application pool.</span></span>
    > <span data-ttu-id="a3a23-121">Сайт пула. ID сайта, на котором находится этот пул.</span><span class="sxs-lookup"><span data-stu-id="a3a23-121">Pool Site: The Site ID of the site on which this pool is homed.</span></span>

4. <span data-ttu-id="a3a23-122">Определите средство SEFAUtil как надежное приложение.</span><span class="sxs-lookup"><span data-stu-id="a3a23-122">Define the SEFAUtil tool as a trusted application.</span></span> <span data-ttu-id="a3a23-123">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="a3a23-123">At the command line, run:</span></span>
    
   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
   ```

    > [!NOTE]
    > <span data-ttu-id="a3a23-124">При необходимости можно использовать другой порт.</span><span class="sxs-lookup"><span data-stu-id="a3a23-124">You can use a different port if needed.</span></span> 
  
5. <span data-ttu-id="a3a23-125">Включить топологию с помощью изменений.</span><span class="sxs-lookup"><span data-stu-id="a3a23-125">Enable the topology with your changes.</span></span> <span data-ttu-id="a3a23-126">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="a3a23-126">At the command line, run:</span></span>
    
   ```powershell
   Enable-CsTopology
   ```

6. <span data-ttu-id="a3a23-127">Если вы еще не сделали этого, скачайте версию Skype для бизнес-сервера средства SEFAUtil из этого расположения [и](https://www.microsoft.com/download/details.aspx?id=52631)установите ее в пул доверенных приложений, созданный на шаге 3.</span><span class="sxs-lookup"><span data-stu-id="a3a23-127">If you haven't already, download the Skype for Business Server version of the SEFAUtil tool from [this location](https://www.microsoft.com/download/details.aspx?id=52631), and install it on the trusted application pool you created in step 3.</span></span>
    
7. <span data-ttu-id="a3a23-128">Убедитесь, что средство SEFAUtil работает правильно, следующим образом:</span><span class="sxs-lookup"><span data-stu-id="a3a23-128">Verify that the SEFAUtil tool is running correctly, as follows:</span></span> 
    
    <span data-ttu-id="a3a23-129">а)</span><span class="sxs-lookup"><span data-stu-id="a3a23-129">a.</span></span> <span data-ttu-id="a3a23-130">Запустите средство из командной подсказки Windows с привилегиями администратора, чтобы отобразить параметры переададации вызовов пользователя в развертывании.</span><span class="sxs-lookup"><span data-stu-id="a3a23-130">Run the tool from the Windows command prompt with administrator privileges to display the call forwarding settings of a user in your deployment.</span></span>
    
    <span data-ttu-id="a3a23-131">б)</span><span class="sxs-lookup"><span data-stu-id="a3a23-131">b.</span></span> <span data-ttu-id="a3a23-132">Отображение параметров переададки вызовов пользователя.</span><span class="sxs-lookup"><span data-stu-id="a3a23-132">Display the call forwarding settings of a user.</span></span> <span data-ttu-id="a3a23-133">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="a3a23-133">At the command line, run:</span></span>
    
   ```console
   SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
   ```

<span data-ttu-id="a3a23-134">Будут отображаться параметры переададки вызовов для пользователя.</span><span class="sxs-lookup"><span data-stu-id="a3a23-134">The call forwarding settings for the user will be displayed.</span></span>
