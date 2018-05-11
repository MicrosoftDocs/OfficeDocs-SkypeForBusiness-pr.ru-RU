---
title: Развертывание инструмента SEFAUtil в Skype для бизнеса 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
description: Развертывание средства SEFAUtil в Скайп для Business Server.
ms.openlocfilehash: 4def73d0bca655569275f61d9ebfeafb4ab7e3d4
ms.sourcegitcommit: b394b394e6c51fe0d75b1eec47f6ada1b0265b63
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/10/2018
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business-2015"></a><span data-ttu-id="05e39-103">Развертывание инструмента SEFAUtil в Skype для бизнеса 2015</span><span class="sxs-lookup"><span data-stu-id="05e39-103">Deploy the SEFAUtil tool in Skype for Business 2015</span></span>
 
<span data-ttu-id="05e39-104">Развертывание средства SEFAUtil в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="05e39-104">Deploying the SEFAUtil tool in Skype for Business Server.</span></span>
  
<span data-ttu-id="05e39-105">Для развертывания и управления раскладки вызывать группу, необходимо использовать Скайп Business Server версии средства SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="05e39-105">To deploy and manage Group Call Pickup, you need to use the Skype for Business Server version of the SEFAUtil tool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="05e39-106">Среда выполнения Microsoft Unified Communications Managed API (UCMA) 5 необходимо установить на любом компьютере, где предполагается запустить средство SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="05e39-106">Microsoft Unified Communications Managed API (UCMA) 5 Runtime must be installed on any computer where you plan to run the SEFAUtil tool.</span></span> <span data-ttu-id="05e39-107">Загружаемый файл расположен здесь: [Объединенных коммуникаций управляемых API 5.0 времени выполнения](https://www.microsoft.com/en-us/download/details.aspx?id=47344).</span><span class="sxs-lookup"><span data-stu-id="05e39-107">Download it here: [Unified Communications Managed API 5.0 Runtime](https://www.microsoft.com/en-us/download/details.aspx?id=47344).</span></span> <span data-ttu-id="05e39-108">Также можно загрузить пакет SDK 5 UCMA, которая включает в себя среды выполнения, здесь: [Пакет SDK для UCMA 5.0](https://www.microsoft.com/en-us/download/details.aspx?id=47345).</span><span class="sxs-lookup"><span data-stu-id="05e39-108">You can also download the UCMA 5 SDK, which includes the runtime, here: [UCMA 5.0 SDK](https://www.microsoft.com/en-us/download/details.aspx?id=47345).</span></span>
  
<span data-ttu-id="05e39-109">Средство SEFAUtil можно запустить в любой пула переднего плана в вашем развертывании.</span><span class="sxs-lookup"><span data-stu-id="05e39-109">You can run the SEFAUtil tool in any Front End pool in your deployment.</span></span> <span data-ttu-id="05e39-110">Для запуска средства SEFAUtil выполните шаги 1, 2 и 3 из Скайп для бизнеса мастер развертывания на компьютере доверенных приложений.</span><span class="sxs-lookup"><span data-stu-id="05e39-110">To run the SEFAUtil tool you must run Steps 1, 2, and 3 from the Skype for Business Deployment Wizard on the Trusted Application Computer.</span></span> <span data-ttu-id="05e39-111">SEFAUtil требует локального хранилища конфигурации должен быть установлен, а также сертификат.</span><span class="sxs-lookup"><span data-stu-id="05e39-111">SEFAUtil requires the local configuration store to be present, as well as a certificate.</span></span>
  
> [!NOTE]
> <span data-ttu-id="05e39-112">Статья блога Technet, посвященной более подробных сведений о запуске SEFAUtil, "[способ получения SEFAutil под управлением?](https://go.microsoft.com/fwlink/?LinkId=278940)«.</span><span class="sxs-lookup"><span data-stu-id="05e39-112">For more details about running SEFAUtil, see the Technet blog article, "[How to get SEFAutil running?](https://go.microsoft.com/fwlink/?LinkId=278940)".</span></span> 
  
### <a name="to-deploy-sefautil"></a><span data-ttu-id="05e39-113">Развертывание SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="05e39-113">To deploy SEFAUtil</span></span>

1. <span data-ttu-id="05e39-114">Войдите на компьютер, где установлена Скайп для консоли Business Server как член группы RTCUniversalServerAdmins или с необходимые права пользователя как описано в **Делегирование разрешений на установку**.</span><span class="sxs-lookup"><span data-stu-id="05e39-114">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="05e39-115">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="05e39-115">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="05e39-116">Средство SEFAUtil может выполняться только на компьютере, который является частью пула доверенных приложений.</span><span class="sxs-lookup"><span data-stu-id="05e39-116">The SEFAUtil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="05e39-117">При необходимости, определение пула доверенных приложений для пула переднего плана, если вы планируете выполнить SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="05e39-117">If needed, define a trusted application pool for the Front End pool where you plan to run SEFAUtil.</span></span> <span data-ttu-id="05e39-118">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="05e39-118">At the command line, run:</span></span>
    
   ```
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```

4. <span data-ttu-id="05e39-p104">Определите инструмент SEFAUtil как доверенное приложение. В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="05e39-p104">Define the SEFAUtil tool as a trusted application. At the command line, run:</span></span>
    
   ```
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
   ```

    > [!NOTE]
    > <span data-ttu-id="05e39-121">При необходимости можно использовать другой порт.</span><span class="sxs-lookup"><span data-stu-id="05e39-121">You can use a different port if needed.</span></span> 
  
5. <span data-ttu-id="05e39-p105">Включите топологию с внесенными изменениями. В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="05e39-p105">Enable the topology with your changes. At the command line, run:</span></span>
    
  ```
  Enable-CsTopology
  ```

6. <span data-ttu-id="05e39-124">Если он еще не установлен, загрузите Скайп Business Server версии средства SEFAUtil из [этого расположения](https://www.microsoft.com/en-us/download/details.aspx?id=52631)и установить его на пул доверенных приложений, созданный на шаге 3.</span><span class="sxs-lookup"><span data-stu-id="05e39-124">If you haven't already, download the Skype for Business Server version of the SEFAUtil tool from [this location](https://www.microsoft.com/en-us/download/details.aspx?id=52631), and install it on the trusted application pool you created in step 3.</span></span>
    
7. <span data-ttu-id="05e39-125">Проверьте правильность работы инструмента SEFAUtil следующим образом.</span><span class="sxs-lookup"><span data-stu-id="05e39-125">Verify that the SEFAUtil tool is running correctly, as follows:</span></span> 
    
    <span data-ttu-id="05e39-126">а.</span><span class="sxs-lookup"><span data-stu-id="05e39-126">a.</span></span> <span data-ttu-id="05e39-127">Запустите этот инструмент из командной строки Windows с привилегиями администратора, чтобы отобразить параметры переадресации звонков пользователя в текущем развертывании.</span><span class="sxs-lookup"><span data-stu-id="05e39-127">Run the tool from the Windows command prompt with administrator privileges to display the call forwarding settings of a user in your deployment.</span></span>
    
    <span data-ttu-id="05e39-128">б.</span><span class="sxs-lookup"><span data-stu-id="05e39-128">b.</span></span> <span data-ttu-id="05e39-129">Отобразите параметры переадресации звонков пользователя.</span><span class="sxs-lookup"><span data-stu-id="05e39-129">Display the call forwarding settings of a user.</span></span> <span data-ttu-id="05e39-130">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="05e39-130">At the command line, run:</span></span>
    
  ```
  SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
  ```

<span data-ttu-id="05e39-131">На экране появятся параметры переадресации звонков пользователя.</span><span class="sxs-lookup"><span data-stu-id="05e39-131">The call forwarding settings for the user will be displayed.</span></span>
    

