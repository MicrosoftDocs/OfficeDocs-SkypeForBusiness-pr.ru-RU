---
title: Перемещение пользователей в локальной Скайп для бизнеса в Интернет
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/27/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 2475674a-f592-4fa8-ae99-f71cbea54dc0
description: 'Сводка: Сведения о перемещении локальных пользователей к Скайп для бизнеса в Интернет.'
ms.openlocfilehash: 09eb62c59ccea1334d7f565a0a49989bff72745b
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="move-on-premises-users-to-skype-for-business-online"></a><span data-ttu-id="9ca14-103">Перемещение пользователей в локальной Скайп для бизнеса в Интернет</span><span class="sxs-lookup"><span data-stu-id="9ca14-103">Move on-premises users to Skype for Business Online</span></span>
 
<span data-ttu-id="9ca14-104">**Сводка:** Сведения о перемещении пользователей в локальной Скайп для бизнеса в Интернет.</span><span class="sxs-lookup"><span data-stu-id="9ca14-104">**Summary:** Information about moving on-premises users to Skype for Business Online.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="9ca14-105">Устройства Lync Phone Edition ДОЛЖНЫ быть обновлены до минимальной версии требуемого встроенного ПО в локальной среде, ДО перехода на Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="9ca14-105">Lync Phone Edition devices MUST be updated to minimum required firmware in your on premises environment PRIOR to moving to Skype for Business Online.</span></span> <span data-ttu-id="9ca14-106">Если перенести пользователей из локальной среды в сетевую версию до обновления встроенного ПО, пользователи не смогут подключаться с помощью телефонов.</span><span class="sxs-lookup"><span data-stu-id="9ca14-106">If you move your users from on-premises to online prior to updating the firmware, users will be unable to connect using their phones.</span></span> <span data-ttu-id="9ca14-107">Для устранения этой проблемы потребуется переместить пользователей обратно в локальную среду, чтобы обновить телефоны до минимальной версии встроенного ПО.</span><span class="sxs-lookup"><span data-stu-id="9ca14-107">To correct this problem, users must be moved back to the on premises environment to have their phones updated to the minimum firmware.</span></span> <span data-ttu-id="9ca14-108">НЕ ПЫТАЙТЕСЬ ВЫПОЛНИТЬ ОБНОВЛЕНИЕ ДО МИНИМАЛЬНОЙ ВЕРСИИ ВСТРОЕННОГО ПО ИЛИ АППАРАТНЫЙ СБРОС НА ТЕЛЕФОНЕ ДО ПЕРЕМЕЩЕНИЯ ПОЛЬЗОВАТЕЛЯ ОБРАТНО В ЛОКАЛЬНУЮ СРЕДУ.</span><span class="sxs-lookup"><span data-stu-id="9ca14-108">DO NOT ATTEMPT TO UPDATE TO MINIMUM FIRMWARE OR HARD RESET THE PHONE PRIOR TO MOVING THE USER BACK TO YOUR ON PREMISES ENVIRONMENT.</span></span>
<span data-ttu-id="9ca14-109">Если аппаратный сброс выполняется на устройстве с устаревшей версией встроенного ПО, по умолчанию используется проверка подлинности PIN-кода, которая не поддерживается в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="9ca14-109">If a hard reset is performed while the device is not at minimum firmware it will default to using PIN Authentication, which is not supported in Skype for Business Online.</span></span> <span data-ttu-id="9ca14-110">Для получения дополнительных сведений обратитесь за помощью к [Началу телефоны для Скайп для бизнеса в Интернет](https://support.office.com/en-us/article/Getting-phones-for-Skype-for-Business-Online-91f2d947-45fc-4fab-bd8b-2e313531c477?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="9ca14-110">For more information, please refer to [Getting Phones for Skype for Business Online](https://support.office.com/en-us/article/Getting-phones-for-Skype-for-Business-Online-91f2d947-45fc-4fab-bd8b-2e313531c477?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
<span data-ttu-id="9ca14-111">Это необязательное действие, которое является обязательным только при перемещении пользователей в локальной Скайп для бизнеса в Интернет.</span><span class="sxs-lookup"><span data-stu-id="9ca14-111">This is an optional step that is required only if you are moving on-premises users to Skype for Business Online.</span></span> <span data-ttu-id="9ca14-112">Перед началом переноса данных пользователей в Скайп для бизнеса в Интернет, проверьте, что Скайп для Business Connector Online (модуля Windows PowerShell) развертывается на серверах переднего плана.</span><span class="sxs-lookup"><span data-stu-id="9ca14-112">Before you begin to move users to Skype for Business Online, check that the Skype for Business Online Connector (Windows PowerShell module) is deployed on your Front End Servers.</span></span> <span data-ttu-id="9ca14-113">Если нет, ее можно загрузить из [центра загрузки](https://www.microsoft.com/en-us/download/details.aspx?id=39366).</span><span class="sxs-lookup"><span data-stu-id="9ca14-113">If it isn't, you can download it from [the download center](https://www.microsoft.com/en-us/download/details.aspx?id=39366).</span></span> <span data-ttu-id="9ca14-114">Кроме того чтобы подготовиться к AD, необходимо настроить подключение Azure AD.</span><span class="sxs-lookup"><span data-stu-id="9ca14-114">Also, to prepare your AD, you'll need to configure Azure AD Connect.</span></span> <span data-ttu-id="9ca14-115">Необходимо использовать версию AAD Connect не ниже 1.0.9125.0.</span><span class="sxs-lookup"><span data-stu-id="9ca14-115">The version of AAD Connect you use must be version 1.0.9125.0 or later.</span></span> <span data-ttu-id="9ca14-116">Если вы используете более раннюю версию средств AAD Connect или DirSync, перейдите на поддерживаемую версию.</span><span class="sxs-lookup"><span data-stu-id="9ca14-116">If you are using an earlier version of AAD Connect tools or DirSync, please upgrade to the supported version.</span></span> <span data-ttu-id="9ca14-117">Вы можете обновить текущую установку или сохранить все настраиваемые правила, определенные в среде.</span><span class="sxs-lookup"><span data-stu-id="9ca14-117">You can upgrade your current installation and maintain any custom rules you have defined in your environment.</span></span>
  
<span data-ttu-id="9ca14-118">Перемещение пользователей с помощью любого из Скайп для панели управления Business Server или Скайп для консоли Business Server в локальном развертывании, но необходимо иметь права администратора для развертывания Office 365.</span><span class="sxs-lookup"><span data-stu-id="9ca14-118">You move users using either Skype for Business Server Control Panel or Skype for Business Server Management Shell in your on-premises deployment, but you must have administrator credentials for your Office 365 deployment.</span></span>
  
## <a name="moving-users-by-using-skype-for-business-control-panel"></a><span data-ttu-id="9ca14-119">Перемещение пользователей с помощью Скайп для панели управления бизнеса</span><span class="sxs-lookup"><span data-stu-id="9ca14-119">Moving users by using Skype for Business Control Panel</span></span>

### <a name="to-move-a-user-to-skype-for-business-online"></a><span data-ttu-id="9ca14-120">Чтобы переместить пользователя Скайп для бизнеса в Интернет</span><span class="sxs-lookup"><span data-stu-id="9ca14-120">To move a user to Skype for Business Online</span></span>

1. <span data-ttu-id="9ca14-121">Учетная запись пользователя, назначенной роли CsUserAdministrator или csadministrator, войдите в систему на любом компьютере во внутреннем развертывании с Скайп для Business Server или на наименее Скайп установлены средства администрирования сервера Business.</span><span class="sxs-lookup"><span data-stu-id="9ca14-121">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment that has Skype for Business Server, or at least Skype for Business Server Admin tools installed.</span></span>
    
2. <span data-ttu-id="9ca14-122">Из меню "Пуск" или ярлык откройте Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="9ca14-122">From the Start menu or desktop shortcut, open the Skype for Business Server Control Panel.</span></span>
    
    <span data-ttu-id="9ca14-123">Вы также можете открыть Скайп для панели управления сервера бизнеса с помощью URL-адрес администрирования, если вы настроили.</span><span class="sxs-lookup"><span data-stu-id="9ca14-123">You can also access the Skype for Business Server Control Panel by using the Admin URL if you have configured one.</span></span>
    
3. <span data-ttu-id="9ca14-124">На панели навигации слева щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="9ca14-124">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="9ca14-125">В поле **Поиск пользователей** введите отображаемое имя или его начальный фрагмент, имя, фамилию, имя учетной записи (диспетчера учетных записей безопасности (SAM), SIP-адрес или строку универсального кода ресурса (URI) из учетной записи пользователя, которому требуется предоставить доступ, затем нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="9ca14-125">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="9ca14-126">Щелкните имя пользователя, затем в меню **Действие** выберите **Переместить выбранных пользователей в Skype для бизнеса Online**.</span><span class="sxs-lookup"><span data-stu-id="9ca14-126">Click the user, then in the **Action** menu, click **Move selected users to Skype for Business Online**.</span></span>
    
6. <span data-ttu-id="9ca14-127">На странице **Перемещение пользователей в Skype для бизнеса Online** прочтите информацию и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="9ca14-127">On the **Move users to Skype For Business Online** page, read the information and then click **Next**.</span></span>
    
7. <span data-ttu-id="9ca14-128">На следующей странице Если вы не еще подписи Office 365, нажмите кнопку **входа в Office 365**, укажите учетные данные и нажмите кнопку **ОК** и **Далее**.</span><span class="sxs-lookup"><span data-stu-id="9ca14-128">On the next page, if you are not yet signed in to Office 365, click **Sign in to Office 365**, provide your credentials, and click **OK** and **Next**.</span></span>
    
8. <span data-ttu-id="9ca14-129">Проверьте правильность числа перемещаемых пользователей и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="9ca14-129">Confirm that the number of users to be moved is correct, and click **Next**.</span></span>
    
9. <span data-ttu-id="9ca14-130">На следующей странице проверьте результаты и нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="9ca14-130">On the next page, review the results and click **Close**.</span></span>
    
## <a name="moving-users-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="9ca14-131">Перемещение пользователей с помощью Скайп для консоли Business Server</span><span class="sxs-lookup"><span data-stu-id="9ca14-131">Moving users by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="9ca14-132">Чтобы переместить локального пользователя вашего Скайп для бизнеса интерактивного клиента, выполните следующие командлеты в Скайп оболочки управления Business Server, используя учетные данные администратора для клиента Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="9ca14-132">To move an on-premises user to your Skype for Business Online tenant, run the following cmdlets in the Skype for Business Server Management Shell, using the administrator credentials for your Microsoft Office 365 tenant.</span></span> <span data-ttu-id="9ca14-133">Замените "username@contoso.com" на информацию о перемещаемом пользователе.</span><span class="sxs-lookup"><span data-stu-id="9ca14-133">Replace "username@contoso.com" with the information for the user that you want to move.</span></span>
  
```
$creds=Get-Credential
```

```
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>
```

<span data-ttu-id="9ca14-134">Формат URL-адрес, указанный для параметра **HostedMigrationOverrideUrl** должен быть URL-адрес в пул, где работает размещенная служба миграции, в следующем формате: _Https://\<полное доменное имя пула\>/HostedMigration/ hostedmigrationService.svc_.</span><span class="sxs-lookup"><span data-stu-id="9ca14-134">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format: _Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc_.</span></span>
  
<span data-ttu-id="9ca14-135">Можно определить URL-адрес размещенной службы миграции, просмотр URL-адрес для Скайп по центру администрирования Online Business для вашей учетной записи клиента Office 365.</span><span class="sxs-lookup"><span data-stu-id="9ca14-135">You can determine the URL to the Hosted Migration Service by viewing the URL for the Skype for Business Online Admin center for your Office 365 tenant account.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9ca14-136">В данном URL-адресе учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="9ca14-136">The URL is case sensitive.</span></span> 
  
### <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a><span data-ttu-id="9ca14-137">Определение URL-адреса размещенной службы миграции для своего клиента Office 365</span><span class="sxs-lookup"><span data-stu-id="9ca14-137">To determine the Hosted Migration Service URL for your Office 365 tenant</span></span>

1. <span data-ttu-id="9ca14-138">Выполните вход в свое клиентское приложение Office 365 как администратор.</span><span class="sxs-lookup"><span data-stu-id="9ca14-138">Login to your Office 365 tenant as an administrator.</span></span>
    
2. <span data-ttu-id="9ca14-139">Откройте **Центр администрирования Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="9ca14-139">Open the **Skype for Business admin center**.</span></span>
    
3. <span data-ttu-id="9ca14-140">Не закрывая окна **Центр администрирования Skype для бизнеса**, выделите и скопируйте URL-адрес в адресную строку в **lync.com**. Примерный URL-адрес выглядит так, как показано далее:</span><span class="sxs-lookup"><span data-stu-id="9ca14-140">With the **Skype for Business admin center** displayed, select and copy the URL in the address bar up to **lync.com**. An example URL looks similar to the following:</span></span>
    
     `https://webdir0a.online.lync.com/lscp/?language=en-US&amp;tenantID=`
    
4. <span data-ttu-id="9ca14-141">Заменяя **webdir** в URL-адресе на **admin**, получаем следующее:</span><span class="sxs-lookup"><span data-stu-id="9ca14-141">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span> 
    
     `https://admin0a.online.lync.com`
    
5. <span data-ttu-id="9ca14-142">Добавьте к URL-адресу следующую строку: **/HostedMigration/hostedmigrationService.svc**.</span><span class="sxs-lookup"><span data-stu-id="9ca14-142">Append the following string to the URL: **/HostedMigration/hostedmigrationService.svc**.</span></span>
    
    <span data-ttu-id="9ca14-143">Полученный URL-адрес, который соответствует значению **HostedMigrationOverrideUrl**, должен выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9ca14-143">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
    
     `https://admin0a.online.lync.com/HostedMigration/hostedmigrationService.svc`
    

