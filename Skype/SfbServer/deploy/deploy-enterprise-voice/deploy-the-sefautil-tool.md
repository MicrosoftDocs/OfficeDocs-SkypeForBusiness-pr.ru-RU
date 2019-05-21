---
title: Развертывание средства Сефаутил в Skype для бизнеса
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
description: Развертывание средства Сефаутил в Skype для бизнеса Server.
ms.openlocfilehash: 74b9ca6fa10237760e84f859baad5188436ac80e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303821"
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business"></a><span data-ttu-id="5652b-103">Развертывание средства Сефаутил в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="5652b-103">Deploy the SEFAUtil tool in Skype for Business</span></span>
 
<span data-ttu-id="5652b-104">Развертывание средства Сефаутил в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="5652b-104">Deploying the SEFAUtil tool in Skype for Business Server.</span></span>
  
<span data-ttu-id="5652b-105">Для развертывания и управления получением группового звонка необходимо использовать версию средства Сефаутил в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="5652b-105">To deploy and manage Group Call Pickup, you need to use the Skype for Business Server version of the SEFAUtil tool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="5652b-106">На любом компьютере, на котором планируется запускать средство Сефаутил, должен быть установлен интерфейс API единой системы обмена сообщениями Microsoft (УКМА) 5.</span><span class="sxs-lookup"><span data-stu-id="5652b-106">Microsoft Unified Communications Managed API (UCMA) 5 Runtime must be installed on any computer where you plan to run the SEFAUtil tool.</span></span> <span data-ttu-id="5652b-107">Загрузите его здесь: [управляемый API единой системы обмена сообщениями 5,0 среды выполнения](https://www.microsoft.com/en-us/download/details.aspx?id=47344).</span><span class="sxs-lookup"><span data-stu-id="5652b-107">Download it here: [Unified Communications Managed API 5.0 Runtime](https://www.microsoft.com/en-us/download/details.aspx?id=47344).</span></span> <span data-ttu-id="5652b-108">Кроме того, вы можете скачать пакет УКМА 5 SDK, который включает среду выполнения: [укма 5,0 SDK](https://www.microsoft.com/en-us/download/details.aspx?id=47345).</span><span class="sxs-lookup"><span data-stu-id="5652b-108">You can also download the UCMA 5 SDK, which includes the runtime, here: [UCMA 5.0 SDK](https://www.microsoft.com/en-us/download/details.aspx?id=47345).</span></span>
  
<span data-ttu-id="5652b-109">Вы можете запустить средство Сефаутил в любом пуле переднего плана в развертывании.</span><span class="sxs-lookup"><span data-stu-id="5652b-109">You can run the SEFAUtil tool in any Front End pool in your deployment.</span></span> <span data-ttu-id="5652b-110">Для запуска средства Сефаутил необходимо выполнить действия 1, 2 и 3 в мастере развертывания Skype для бизнеса на доверенном компьютере приложения.</span><span class="sxs-lookup"><span data-stu-id="5652b-110">To run the SEFAUtil tool you must run Steps 1, 2, and 3 from the Skype for Business Deployment Wizard on the Trusted Application Computer.</span></span> <span data-ttu-id="5652b-111">Для Сефаутил требуется, чтобы локальное хранилище конфигурации присутствовало и для сертификата.</span><span class="sxs-lookup"><span data-stu-id="5652b-111">SEFAUtil requires the local configuration store to be present, as well as a certificate.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5652b-112">Дополнительные сведения о том, как запустить Сефаутил, можно найти в статье блога "[как получить сефаутил на работе?](https://go.microsoft.com/fwlink/?LinkId=278940)".</span><span class="sxs-lookup"><span data-stu-id="5652b-112">For more details about running SEFAUtil, see the  blog article, "[How to get SEFAutil running?](https://go.microsoft.com/fwlink/?LinkId=278940)".</span></span> 
  
### <a name="to-deploy-sefautil"></a><span data-ttu-id="5652b-113">Развертывание SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="5652b-113">To deploy SEFAUtil</span></span>

1. <span data-ttu-id="5652b-114">Войдите в систему на компьютере, на котором установлена консоль управления Skype для бизнеса Server, в качестве участника группы Рткуниверсалсерверадминс или с необходимыми правами пользователя, описанными в разделе **Делегирование разрешений на настройку**.</span><span class="sxs-lookup"><span data-stu-id="5652b-114">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="5652b-115">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="5652b-115">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="5652b-116">The SEFAUtil tool can be run only on a computer that is part of a trusted application pool.</span><span class="sxs-lookup"><span data-stu-id="5652b-116">The SEFAUtil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="5652b-117">При необходимости определите доверенный пул приложений для пула переднего плана, в котором планируется запускать Сефаутил.</span><span class="sxs-lookup"><span data-stu-id="5652b-117">If needed, define a trusted application pool for the Front End pool where you plan to run SEFAUtil.</span></span> <span data-ttu-id="5652b-118">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="5652b-118">At the command line, run:</span></span>
    
   ```
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```
    > [!NOTE]
    > <span data-ttu-id="5652b-119">Полное доменное имя пула: полное доменное имя сервера или пула, на котором будет размещено приложение Сефаутил (обычно это интерфейс сервера или пула Skype для бизнеса).</span><span class="sxs-lookup"><span data-stu-id="5652b-119">Pool FQDN: The FQDN of the server or pool that will host the SEFAUtil application (usually a Skype for Business Front End server or pool).</span></span>
    > <span data-ttu-id="5652b-120">Полное доменное имя регистратора пула: полное доменное имя сервера или пула приложений Skype для бизнеса, связанного с этим пулом.</span><span class="sxs-lookup"><span data-stu-id="5652b-120">Pool Registrar FQDN: The FQDN of the Skype for Business Front End server or pool associated with this application pool.</span></span>
    > <span data-ttu-id="5652b-121">Сайт пула: идентификатор сайта, на котором находится этот пул.</span><span class="sxs-lookup"><span data-stu-id="5652b-121">Pool Site: The Site ID of the site on which this pool is homed.</span></span>

4. <span data-ttu-id="5652b-p105">Определите инструмент SEFAUtil как доверенное приложение. В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="5652b-p105">Define the SEFAUtil tool as a trusted application. At the command line, run:</span></span>
    
   ```
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
   ```

    > [!NOTE]
    > <span data-ttu-id="5652b-124">При необходимости можно использовать другой порт.</span><span class="sxs-lookup"><span data-stu-id="5652b-124">You can use a different port if needed.</span></span> 
  
5. <span data-ttu-id="5652b-p106">Включите топологию с внесенными изменениями. В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="5652b-p106">Enable the topology with your changes. At the command line, run:</span></span>
    
   ```
   Enable-CsTopology
   ```

6. <span data-ttu-id="5652b-127">Если вы еще не сделали это, Скачайте версию средства Сефаутил в Skype для бизнеса Server из [этого расположения](https://www.microsoft.com/en-us/download/details.aspx?id=52631)и установите ее в доверенной группе приложений, созданной в действии 3.</span><span class="sxs-lookup"><span data-stu-id="5652b-127">If you haven't already, download the Skype for Business Server version of the SEFAUtil tool from [this location](https://www.microsoft.com/en-us/download/details.aspx?id=52631), and install it on the trusted application pool you created in step 3.</span></span>
    
7. <span data-ttu-id="5652b-128">Проверьте правильность работы инструмента SEFAUtil следующим образом.</span><span class="sxs-lookup"><span data-stu-id="5652b-128">Verify that the SEFAUtil tool is running correctly, as follows:</span></span> 
    
    <span data-ttu-id="5652b-129">a)</span><span class="sxs-lookup"><span data-stu-id="5652b-129">a.</span></span> <span data-ttu-id="5652b-130">Запустите этот инструмент из командной строки Windows с привилегиями администратора, чтобы отобразить параметры переадресации звонков пользователя в текущем развертывании.</span><span class="sxs-lookup"><span data-stu-id="5652b-130">Run the tool from the Windows command prompt with administrator privileges to display the call forwarding settings of a user in your deployment.</span></span>
    
    <span data-ttu-id="5652b-131">б)</span><span class="sxs-lookup"><span data-stu-id="5652b-131">b.</span></span> <span data-ttu-id="5652b-132">Отобразите параметры переадресации звонков пользователя.</span><span class="sxs-lookup"><span data-stu-id="5652b-132">Display the call forwarding settings of a user.</span></span> <span data-ttu-id="5652b-133">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="5652b-133">At the command line, run:</span></span>
    
   ```
   SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
   ```

<span data-ttu-id="5652b-134">На экране появятся параметры переадресации звонков пользователя.</span><span class="sxs-lookup"><span data-stu-id="5652b-134">The call forwarding settings for the user will be displayed.</span></span>
    

