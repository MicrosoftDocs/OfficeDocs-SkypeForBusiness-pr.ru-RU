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
ms.openlocfilehash: 20cda161c182c8dfb426f61b793366b7f60f37d5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812389"
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business"></a><span data-ttu-id="fb358-103">Развертывание средства SEFAUtil в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="fb358-103">Deploy the SEFAUtil tool in Skype for Business</span></span>
 
<span data-ttu-id="fb358-104">Развертывание средства SEFAUtil в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="fb358-104">Deploying the SEFAUtil tool in Skype for Business Server.</span></span>
  
<span data-ttu-id="fb358-105">Для развертывания группового средства группового вызова и управления им необходимо использовать версию средства SEFAUtil в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="fb358-105">To deploy and manage Group Call Pickup, you need to use the Skype for Business Server version of the SEFAUtil tool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="fb358-106">Microsoft Unified Communications Managed API (UCMA) 5 Runtime must be installed on any computer where you plan to run the SEFAUtil tool.</span><span class="sxs-lookup"><span data-stu-id="fb358-106">Microsoft Unified Communications Managed API (UCMA) 5 Runtime must be installed on any computer where you plan to run the SEFAUtil tool.</span></span> <span data-ttu-id="fb358-107">Скачайте его здесь: [unified Communications Managed API 5.0 Runtime](https://www.microsoft.com/download/details.aspx?id=47344).</span><span class="sxs-lookup"><span data-stu-id="fb358-107">Download it here: [Unified Communications Managed API 5.0 Runtime](https://www.microsoft.com/download/details.aspx?id=47344).</span></span> <span data-ttu-id="fb358-108">Вы также можете скачать SDK UCMA 5, который включает time runtime, здесь: [UCMA 5.0 SDK](https://www.microsoft.com/download/details.aspx?id=47345).</span><span class="sxs-lookup"><span data-stu-id="fb358-108">You can also download the UCMA 5 SDK, which includes the runtime, here: [UCMA 5.0 SDK](https://www.microsoft.com/download/details.aspx?id=47345).</span></span>
  
<span data-ttu-id="fb358-109">Средство SEFAUtil можно запустить в любом пуле переднего входа в развертывании.</span><span class="sxs-lookup"><span data-stu-id="fb358-109">You can run the SEFAUtil tool in any Front End pool in your deployment.</span></span> <span data-ttu-id="fb358-110">Чтобы запустить средство SEFAUtil, необходимо выполнить шаги 1, 2 и 3 в мастере развертывания Skype для бизнеса на компьютере доверенного приложения.</span><span class="sxs-lookup"><span data-stu-id="fb358-110">To run the SEFAUtil tool you must run Steps 1, 2, and 3 from the Skype for Business Deployment Wizard on the Trusted Application Computer.</span></span> <span data-ttu-id="fb358-111">ДЛЯ SEFAUtil требуется локальное хранилище конфигурации, а также сертификат.</span><span class="sxs-lookup"><span data-stu-id="fb358-111">SEFAUtil requires the local configuration store to be present, as well as a certificate.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fb358-112">Дополнительные сведения о запуске SEFAUtil см. в статье блога["Как запускать SEFAutil?"](https://go.microsoft.com/fwlink/?LinkId=278940)</span><span class="sxs-lookup"><span data-stu-id="fb358-112">For more details about running SEFAUtil, see the  blog article, "[How to get SEFAutil running?](https://go.microsoft.com/fwlink/?LinkId=278940)".</span></span> 
  
### <a name="to-deploy-sefautil"></a><span data-ttu-id="fb358-113">Развертывание SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="fb358-113">To deploy SEFAUtil</span></span>

1. <span data-ttu-id="fb358-114">Войдите на компьютер, на котором установлена оболочка управления Skype для бизнеса Server, в качестве члена группы RTCUniversalServerAdmins или с необходимыми правами пользователя, как описано в делегирования разрешений на **установку.**</span><span class="sxs-lookup"><span data-stu-id="fb358-114">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="fb358-115">Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**</span><span class="sxs-lookup"><span data-stu-id="fb358-115">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="fb358-116">Средство SEFAUtil можно запустить только на компьютере, который входит в пул доверенных приложений.</span><span class="sxs-lookup"><span data-stu-id="fb358-116">The SEFAUtil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="fb358-117">При необходимости определите пул доверенных приложений для пула переднего плана, в котором планируется запустить SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="fb358-117">If needed, define a trusted application pool for the Front End pool where you plan to run SEFAUtil.</span></span> <span data-ttu-id="fb358-118">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="fb358-118">At the command line, run:</span></span>
    
   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```
    > [!NOTE]
    > <span data-ttu-id="fb358-119">FQDN пула: FQDN сервера или пула, на который будет работать приложение SEFAUtil (обычно это сервер или пул переднего сервера Skype для бизнеса).</span><span class="sxs-lookup"><span data-stu-id="fb358-119">Pool FQDN: The FQDN of the server or pool that will host the SEFAUtil application (usually a Skype for Business Front End server or pool).</span></span>
    > <span data-ttu-id="fb358-120">FQDN регистратора пулов: FQDN сервера переднего сервера или пула Skype для бизнеса, связанного с этим пулом приложений.</span><span class="sxs-lookup"><span data-stu-id="fb358-120">Pool Registrar FQDN: The FQDN of the Skype for Business Front End server or pool associated with this application pool.</span></span>
    > <span data-ttu-id="fb358-121">Сайт пула: ИД сайта, на котором находится этот пул.</span><span class="sxs-lookup"><span data-stu-id="fb358-121">Pool Site: The Site ID of the site on which this pool is homed.</span></span>

4. <span data-ttu-id="fb358-122">Определите средство SEFAUtil как доверенного приложения.</span><span class="sxs-lookup"><span data-stu-id="fb358-122">Define the SEFAUtil tool as a trusted application.</span></span> <span data-ttu-id="fb358-123">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="fb358-123">At the command line, run:</span></span>
    
   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
   ```

    > [!NOTE]
    > <span data-ttu-id="fb358-124">При необходимости можно использовать другой порт.</span><span class="sxs-lookup"><span data-stu-id="fb358-124">You can use a different port if needed.</span></span> 
  
5. <span data-ttu-id="fb358-125">В включить топологию с изменениями.</span><span class="sxs-lookup"><span data-stu-id="fb358-125">Enable the topology with your changes.</span></span> <span data-ttu-id="fb358-126">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="fb358-126">At the command line, run:</span></span>
    
   ```powershell
   Enable-CsTopology
   ```

6. <span data-ttu-id="fb358-127">Если вы еще не сделали этого, скачайте версию средства SEFAUtil в Skype для бизнеса Server из этого расположения и установите ее в пул доверенных приложений, созданный на шаге 3. [](https://www.microsoft.com/download/details.aspx?id=52631)</span><span class="sxs-lookup"><span data-stu-id="fb358-127">If you haven't already, download the Skype for Business Server version of the SEFAUtil tool from [this location](https://www.microsoft.com/download/details.aspx?id=52631), and install it on the trusted application pool you created in step 3.</span></span>
    
7. <span data-ttu-id="fb358-128">Убедитесь, что средство SEFAUtil работает правильно:</span><span class="sxs-lookup"><span data-stu-id="fb358-128">Verify that the SEFAUtil tool is running correctly, as follows:</span></span> 
    
    <span data-ttu-id="fb358-129">а.</span><span class="sxs-lookup"><span data-stu-id="fb358-129">a.</span></span> <span data-ttu-id="fb358-130">Запустите средство в командной панели Windows с привилегиями администратора, чтобы отобразить параметры переадминации вызовов пользователя в развертывании.</span><span class="sxs-lookup"><span data-stu-id="fb358-130">Run the tool from the Windows command prompt with administrator privileges to display the call forwarding settings of a user in your deployment.</span></span>
    
    <span data-ttu-id="fb358-131">б.</span><span class="sxs-lookup"><span data-stu-id="fb358-131">b.</span></span> <span data-ttu-id="fb358-132">Отображение параметров переад вызовов пользователя.</span><span class="sxs-lookup"><span data-stu-id="fb358-132">Display the call forwarding settings of a user.</span></span> <span data-ttu-id="fb358-133">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="fb358-133">At the command line, run:</span></span>
    
   ```console
   SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
   ```

<span data-ttu-id="fb358-134">Отобразить параметры переададантки вызовов для пользователя.</span><span class="sxs-lookup"><span data-stu-id="fb358-134">The call forwarding settings for the user will be displayed.</span></span>
    

