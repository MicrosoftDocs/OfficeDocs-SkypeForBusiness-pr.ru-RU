---
title: Подготовка учетных записей системы комнат Skype в Microsoft 365 и Office 365
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c36150bb-461c-4f1c-877b-fac7fb232f7c
description: В этом разделе содержится информация о предоставлении учетных записей системы комнат Skype в Microsoft 365 или Office 365.
ms.openlocfilehash: 115dd83751e0da837d9d88351d57a769b7e313da
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820849"
---
# <a name="provisioning-skype-room-system-accounts-in-microsoft-365-and-office-365"></a><span data-ttu-id="e7482-103">Подготовка учетных записей системы комнат Skype в Microsoft 365 и Office 365</span><span class="sxs-lookup"><span data-stu-id="e7482-103">Provisioning Skype Room System accounts in Microsoft 365 and Office 365</span></span>
 
<span data-ttu-id="e7482-104">В этом разделе содержится информация о предоставлении учетных записей системы комнат Skype в Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="e7482-104">Read this topic to learn about provisioning Skype Room System accounts in Microsoft 365 or Office 365.</span></span>
  
<span data-ttu-id="e7482-105">В следующем разделе описывается подготовка учетной записи системы комнат Skype.</span><span class="sxs-lookup"><span data-stu-id="e7482-105">The following section covers Skype Room System account provisioning.</span></span>
  
## <a name="microsoft-365-and-office-365-prerequisites"></a><span data-ttu-id="e7482-106">Предварительные условия для Microsoft 365 и Office 365</span><span class="sxs-lookup"><span data-stu-id="e7482-106">Microsoft 365 and Office 365 prerequisites</span></span>

<span data-ttu-id="e7482-107">Ваш сетевой клиент должен соответствовать следующим требованиям:</span><span class="sxs-lookup"><span data-stu-id="e7482-107">Your online tenant must meet the following requirements:</span></span>
  
- <span data-ttu-id="e7482-108">План Microsoft 365 или Office 365 должен включать Skype для бизнеса Online (план 2) или Office 365 E1, E3 или E5.</span><span class="sxs-lookup"><span data-stu-id="e7482-108">The Microsoft 365 or Office 365 plan must include Skype for Business Online Plan 2, or Office 365 E1, E3 or E5.</span></span> <br/><span data-ttu-id="e7482-109">Подробные сведения о планах Skype для бизнеса Online см. в [описании службы Skype для бизнеса Online.](https://technet.microsoft.com/library/jj822172.aspx)</span><span class="sxs-lookup"><span data-stu-id="e7482-109">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span></span>
    
- <span data-ttu-id="e7482-110">В клиенте должна быть включена возможность работы со Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="e7482-110">Your tenant must have the conferencing capability of Skype for Business enabled.</span></span>
    
- <span data-ttu-id="e7482-111">В клиенте должна быть включена exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e7482-111">Your tenant must have Exchange Online enabled.</span></span> 
    
- <span data-ttu-id="e7482-112">Удаленный администратор клиента должен иметь следующий доступ к PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e7482-112">Your tenant remote administrator must have the following PowerShell access:</span></span>
    
  - <span data-ttu-id="e7482-113">Удаленный доступ к PowerShell для Exchange</span><span class="sxs-lookup"><span data-stu-id="e7482-113">Exchange Remote PowerShell access</span></span>
    
  - <span data-ttu-id="e7482-114">Удаленный доступ к PowerShell в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="e7482-114">Skype for Business Online Remote PowerShell access</span></span>
    
  - <span data-ttu-id="e7482-115">Windows Azure active Directory для Windows PowerShell доступа к каталогам Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="e7482-115">Windows Azure Active Directory Module for Windows PowerShell to access Microsoft 365 or Office 365 directory access</span></span>
    
<span data-ttu-id="e7482-116">Для учетной записи комнат Skype требуется следующее лицензирование:</span><span class="sxs-lookup"><span data-stu-id="e7482-116">For the Skype Room account, the following licensing is required:</span></span>
  
- <span data-ttu-id="e7482-117">Чтобы включить собрания Skype, необходима лицензия Skype для бизнеса Online (план 2) или Office 365 E1 или E3.</span><span class="sxs-lookup"><span data-stu-id="e7482-117">A Skype for Business Online Plan 2 or Office 365 E1 or E3 license is required to enable Skype Meetings.</span></span>
    
- <span data-ttu-id="e7482-118">Чтобы сделать комнату с возможностью Корпоративная голосовая связь, чтобы в нее можно было включить номер телефона, требуется Skype для бизнеса Online (план 2) с лицензией на телефонную систему или Office 365 E5 (1).</span><span class="sxs-lookup"><span data-stu-id="e7482-118">To entitle the room with the Enterprise Voice capability so the room can be enabled with a phone number, a Skype for Business Online Plan 2 with the Phone System license or Office 365 E5 is required (1).</span></span>
    
- <span data-ttu-id="e7482-119">Если вам требуются возможности телефонного звонка на собрании, вам потребуется лицензия на аудиоконференцию и телефонную систему.</span><span class="sxs-lookup"><span data-stu-id="e7482-119">If you need dial-in capabilities from a meeting, you will need an audio conferencing and Phone System license.</span></span>  <span data-ttu-id="e7482-120">Если вам требуются возможности телефонного звонка на собрании, вам потребуется план внутренних или внутренних и международных звонков.</span><span class="sxs-lookup"><span data-stu-id="e7482-120">If you need dial-out capabilities from a meeting, you will need a domestic or domestic and international Calling Plan.</span></span> 
    
- <span data-ttu-id="e7482-121">Лицензия Exchange Online не требуется для учетной записи комнаты Skype, так как она должна быть настроена как учетная запись почтового ящика ресурса.</span><span class="sxs-lookup"><span data-stu-id="e7482-121">An Exchange Online license is not required for the Skype Room account because the account should be configured as a resource mailbox account.</span></span>
    
## <a name="provisioning-overview"></a><span data-ttu-id="e7482-122">Общие сведения о подготовках</span><span class="sxs-lookup"><span data-stu-id="e7482-122">Provisioning overview</span></span>

<span data-ttu-id="e7482-123">На следующей схеме представлен обзор потока предоставления учетной записи системы комнат Skype.</span><span class="sxs-lookup"><span data-stu-id="e7482-123">The following diagram provides an overview of the Skype Room System account provisioning flow.</span></span>
  
![Этапы предоставления системы комнат Skype](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a><span data-ttu-id="e7482-125">Определение нового конференц-зала</span><span class="sxs-lookup"><span data-stu-id="e7482-125">Identify a new conference room</span></span>

<span data-ttu-id="e7482-126">Возможно, у вас уже есть почтовый ящик помещения ресурсов в Exchange, который предоставляет функцию планирования, или вы можете создать почтовый ящик ресурса в первый раз для упрощения развертывания системы комнат Skype.</span><span class="sxs-lookup"><span data-stu-id="e7482-126">You may already have a resource room mailbox in Exchange that provides the scheduling feature, or you may be creating a resource mailbox for the first time to facilitate Skype Room System deployment.</span></span> <span data-ttu-id="e7482-127">В любом случае необходимо определить учетную запись помещения, которая будет использоваться в клиенте.</span><span class="sxs-lookup"><span data-stu-id="e7482-127">In any case, you must identify a room account to be used in your tenant.</span></span> <span data-ttu-id="e7482-128">Разделы "Подготовка Exchange Online" и "Подготовка Skype для бизнеса" предоставляют руководство по обоим типам учетных записей.</span><span class="sxs-lookup"><span data-stu-id="e7482-128">The Exchange Online Provision and Skype for Business Provision sections provide guidance for both kinds of accounts.</span></span> <span data-ttu-id="e7482-129">Например, предположим, что у вас есть две следующие комнаты, и вы хотите развернуть систему комнат Skype для обеих комнат:</span><span class="sxs-lookup"><span data-stu-id="e7482-129">For example, let's say you have the following two rooms, and you would like to deploy Skype Room System for both of them:</span></span>
  
- <span data-ttu-id="e7482-130">Существующая учетная запись почтового ящика ресурса: confrm1@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="e7482-130">Existing Resource Mailbox Account: confrm1@contoso.onmicrosoft.com</span></span>
    
- <span data-ttu-id="e7482-131">Новая учетная запись почтового ящика ресурса: confrm2@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="e7482-131">New Resource Mailbox Account: confrm2@contoso.onmicrosoft.com</span></span>
    
## <a name="exchange-online-provisioning"></a><span data-ttu-id="e7482-132">Подготовка Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e7482-132">Exchange Online provisioning</span></span>

<span data-ttu-id="e7482-133">Сначала подключите Exchange Online PowerShell, следуя инструкциям в этой теме, подключите [к Exchange Online PowerShell.](https://go.microsoft.com/fwlink/p/?LinkId=396554)</span><span class="sxs-lookup"><span data-stu-id="e7482-133">First, connect to Exchange Online PowerShell by following the instructions in the topic, [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
  
<span data-ttu-id="e7482-134">Чтобы настроить существующую учетную запись почтового ящика помещения ресурсов для системы комнат Skype, в Exchange Online PowerShell запустите следующие команды:</span><span class="sxs-lookup"><span data-stu-id="e7482-134">To set an existing resource room mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```powershell
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="e7482-135">Чтобы создать новую учетную запись почтового ящика ресурса Exchange для системы комнат Skype, в Exchange Online PowerShell запустите следующие команды:</span><span class="sxs-lookup"><span data-stu-id="e7482-135">To create a new Exchange resource mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```powershell
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="e7482-136">Предыдущие команды позволяют настроить или создать новую учетную запись почтового ящика ресурса Exchange для использования системы комнат Skype, включив учетную запись.</span><span class="sxs-lookup"><span data-stu-id="e7482-136">The previous commands set up or create a new Exchange resource mailbox account for Skype Room System usage by enabling the account.</span></span>
  
<span data-ttu-id="e7482-137">После создания почтового ящика можно использовать Set-CalendarProcessing в Exchange Online PowerShell для настройки почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="e7482-137">After creating the mailbox, you can use the Set-CalendarProcessing cmdlet in Exchange Online PowerShell to configure the mailbox.</span></span> <span data-ttu-id="e7482-138">Дополнительные сведения о шагах 3-6 в локальном развертывании с одним лесом</span><span class="sxs-lookup"><span data-stu-id="e7482-138">Refer to steps 3 through 6 under Single forest on-premises deployments for more details</span></span>

## <a name="assigning-a-skype-for-business-online-license"></a><span data-ttu-id="e7482-139">Назначение лицензии Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="e7482-139">Assigning a Skype for Business Online license</span></span>

<span data-ttu-id="e7482-140">Теперь вы можете назначить лицензию на Skype для бизнеса Online (план 2) или Skype для бизнеса Online (план 3) с помощью портала администрирования Microsoft 365, как описано в описании назначения или удаления лицензий для [Microsoft 365](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) для бизнеса или лицензирования надстройки [Skype](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="e7482-140">Now you can assign a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license by using the Microsoft 365 administrative portal as described in [Assign or remove licenses for Microsoft 365 for business](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) or in [Skype for Business add-on licensing](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7).</span></span> 
  
<span data-ttu-id="e7482-141">После назначения лицензии для Skype для бизнеса Online вы сможете войти в систему и проверить, активна ли учетная запись, с помощью любого клиента Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="e7482-141">After you assign a license for Skype for Business Online, you will be able to log in and validate that the account is active using any Skype for Business client.</span></span>
  
## <a name="skype-for-business-online-provisioning"></a><span data-ttu-id="e7482-142">Подготовка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="e7482-142">Skype for Business Online provisioning</span></span>

<span data-ttu-id="e7482-143">После создания и включения учетной записи почтового ящика помещения ресурсов, как показано ранее, и лицензирования учетной записи Skype для бизнеса Online учетная запись будет синхронизироваться из леса Exchange Online с лесом Skype для бизнеса Online с помощью Windows Azure леса Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e7482-143">After a resource room mailbox account has been created and enabled as shown previously, and you have licensed the account for Skype For Business Online the account will synchronize from the Exchange Online forest to Skype for Business Online forest by using the Windows Azure Active Directory forest.</span></span> <span data-ttu-id="e7482-144">Для предоставления учетной записи системы комнат Skype в пуле Skype для бизнеса Online необходимо сделать следующее.</span><span class="sxs-lookup"><span data-stu-id="e7482-144">The following steps are required to provision the Skype Room System account in the Skype for Business Online pool.</span></span> <span data-ttu-id="e7482-145">Эти действия одинаковы как для существующей учетной записи почтового ящика ресурса, так и для вновь созданной учетной записи (confrm1 или confrm2), так как после включения в Exchange Online обе эти учетные записи будут синхронизированы со Skype для бизнеса Online таким же образом:</span><span class="sxs-lookup"><span data-stu-id="e7482-145">These steps are the same for both an existing resource mailbox account or a newly created account (confrm1 or confrm2), because once they are enabled in Exchange Online, both of these accounts will be synchronized to Skype for Business Online in the same way:</span></span>
  
1. <span data-ttu-id="e7482-146">Создание удаленного сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e7482-146">Create a Remote PowerShell session.</span></span> <span data-ttu-id="e7482-147">Обратите внимание, что вам потребуется скачать модуль соединителю Skype для бизнеса Online и Microsoft Online Services Sign-In помощника и убедиться, что компьютер настроен.</span><span class="sxs-lookup"><span data-stu-id="e7482-147">Note that you will need to download Skype for Business Online Connector Module and Microsoft Online Services Sign-In Assistant and make sure that your computer is configured.</span></span> <span data-ttu-id="e7482-148">Дополнительные сведения [см.](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)в этой Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e7482-148">For more information, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
    
   ```powershell
   Import-Module LyncOnlineConnector
   $cssess=New-CsOnlineSession -Credential $cred
   Import-PSSession $cssess -AllowClobber
   ```

2. <span data-ttu-id="e7482-149">Чтобы включить учетную запись системы комнат Skype для Skype для бизнеса, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e7482-149">To enable an Skype Room System account for Skype for Business, run the following command:</span></span>
    
   ```powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    <span data-ttu-id="e7482-150">Чтобы получить это свойство, вы можете получить адрес RegistrarPool, на котором находятся пользователи Skype для бизнеса, из одной из существующих учетных записей, используя следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e7482-150">You can obtain the RegistrarPool address where your Skype for Business users are homed from one of your existing accounts by using the following command to returns this property:</span></span>
    
   ```powershell
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

>[!NOTE] 
><span data-ttu-id="e7482-151">Многофакторная проверка подлинности (MFA) не поддерживается для учетных записей системы комнат Skype.</span><span class="sxs-lookup"><span data-stu-id="e7482-151">Multi-Factor Authentication (MFA) isn't supported for Skype Room System accounts.</span></span> 

## <a name="password-expiration"></a><span data-ttu-id="e7482-152">Срок действия пароля</span><span class="sxs-lookup"><span data-stu-id="e7482-152">Password expiration</span></span>

<span data-ttu-id="e7482-153">В Microsoft 365 или Office 365 политика срока действия паролей по умолчанию для всех учетных записей пользователей составляет 90 дней, если вы не настроите другую политику срока действия паролей.</span><span class="sxs-lookup"><span data-stu-id="e7482-153">In Microsoft 365 or Office 365, the default password expiration policy for all of your user accounts is 90 days unless you configure a different password expiration policy.</span></span> <span data-ttu-id="e7482-154">Для учетных записей системы комнат Skype можно выбрать параметр "Срок действия пароля никогда не истекает", вы можете сделать следующее.</span><span class="sxs-lookup"><span data-stu-id="e7482-154">For Skype Room System accounts, you can select the Password never expires setting with the following steps.</span></span>
  
1. <span data-ttu-id="e7482-155">Создайте сеанс Windows Azure Active Directory, используя учетные данные глобального администратора клиента.</span><span class="sxs-lookup"><span data-stu-id="e7482-155">Create a Windows Azure Active Directory session by using your tenant global administrator credentials.</span></span>
    
    ```powershell
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. <span data-ttu-id="e7482-156">Установите параметр "Срок действия пароля не истекает" для учетной записи системы комнат Skype, созданной ранее, с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="e7482-156">Set the Password never expires setting for the Skype Room System room account created previously by using the following command:</span></span>
    
   ```powershell
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

<span data-ttu-id="e7482-157">Дополнительные сведения [см.](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)в этой Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e7482-157">For more information, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  
## <a name="validate"></a><span data-ttu-id="e7482-158">Проверка</span><span class="sxs-lookup"><span data-stu-id="e7482-158">Validate</span></span>

<span data-ttu-id="e7482-159">Для проверки вы должны иметь возможность использовать любой клиент Skype для бизнеса, чтобы войти в созданную учетную запись.</span><span class="sxs-lookup"><span data-stu-id="e7482-159">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>

