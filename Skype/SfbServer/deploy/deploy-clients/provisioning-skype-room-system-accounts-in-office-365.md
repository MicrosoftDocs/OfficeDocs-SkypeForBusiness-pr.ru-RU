---
title: Предоставление учетных записей системы комнат Skype в Office 365
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c36150bb-461c-4f1c-877b-fac7fb232f7c
description: В этом разделе описывается выделение учетных записей системы комнат Skype в Office 365.
ms.openlocfilehash: 63b195dd2989e6da2d3a2cecdbc76ccff741cd87
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "21010043"
---
# <a name="provisioning-skype-room-system-accounts-in-office-365"></a><span data-ttu-id="9f170-103">Предоставление учетных записей системы комнат Skype в Office 365</span><span class="sxs-lookup"><span data-stu-id="9f170-103">Provisioning Skype Room System accounts in Office 365</span></span>
 
<span data-ttu-id="9f170-104">В этом разделе описывается выделение учетных записей системы комнат Skype в Office 365.</span><span class="sxs-lookup"><span data-stu-id="9f170-104">Read this topic to learn about provisioning Skype Room System accounts in Office 365.</span></span>
  
<span data-ttu-id="9f170-105">В данном разделе рассматриваются Скайп комнаты системной учетной записью, подготовки для клиента Office 365.</span><span class="sxs-lookup"><span data-stu-id="9f170-105">The following section covers Skype Room System account provisioning for an Office 365 tenant.</span></span>
  
## <a name="office-365-prerequisites"></a><span data-ttu-id="9f170-106">Предварительные требования для Office 365</span><span class="sxs-lookup"><span data-stu-id="9f170-106">Office 365 prerequisites</span></span>

<span data-ttu-id="9f170-107">Сетевой клиент должен удовлетворять следующим требованиям:</span><span class="sxs-lookup"><span data-stu-id="9f170-107">Your online tenant must meet the following requirements:</span></span>
  
- <span data-ttu-id="9f170-108">Скайп необходимо включить в план Office 365 для бизнеса Online план 2, 3 план или Office 365 E1, E3 или E5.</span><span class="sxs-lookup"><span data-stu-id="9f170-108">The Office 365 plan must include Skype for Business Online Plan 2, Plan 3, or Office 365 E1, E3 or E5.</span></span>
    
- <span data-ttu-id="9f170-109">Клиент должен иметь возможности конференц-связи Скайп для бизнеса включен.</span><span class="sxs-lookup"><span data-stu-id="9f170-109">Your tenant must have the conferencing capability of Skype for Business enabled.</span></span>
    
- <span data-ttu-id="9f170-110">У пользователя должно быть включено приложение Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="9f170-110">Your tenant must have Exchange Online enabled.</span></span> 
    
- <span data-ttu-id="9f170-111">Удаленный администратор пользователя должен иметь следующие права доступа PowerShell:</span><span class="sxs-lookup"><span data-stu-id="9f170-111">Your tenant remote administrator must have the following PowerShell access:</span></span>
    
  - <span data-ttu-id="9f170-112">Удаленный доступ PowerShell к Exchange</span><span class="sxs-lookup"><span data-stu-id="9f170-112">Exchange Remote PowerShell access</span></span>
    
  - <span data-ttu-id="9f170-113">Скайп для доступа к Business Online удаленной оболочки PowerShell</span><span class="sxs-lookup"><span data-stu-id="9f170-113">Skype for Business Online Remote PowerShell access</span></span>
    
  - <span data-ttu-id="9f170-114">Windows Azure модуль Active Directory для Windows PowerShell для доступа к Office 365 доступ к каталогу</span><span class="sxs-lookup"><span data-stu-id="9f170-114">Windows Azure Active Directory Module for Windows PowerShell to access Office 365 directory access</span></span>
    
<span data-ttu-id="9f170-115">Для учетной записи комнаты Skype необходимы следующие лицензии::</span><span class="sxs-lookup"><span data-stu-id="9f170-115">For the Skype Room account, the following licensing is required:</span></span>
  
- <span data-ttu-id="9f170-116">Скайп для бизнеса Online (план 2) или Office 365 E1 или E3 лицензия требуется для включения Скайп собрания.</span><span class="sxs-lookup"><span data-stu-id="9f170-116">A Skype for Business Online Plan 2 or Office 365 E1 or E3 license is required to enable Skype Meetings.</span></span>
    
- <span data-ttu-id="9f170-117">Для предоставления комнаты с возможностью корпоративной голосовой связи, поэтому комнаты можно включить с номером телефона, Скайп для бизнеса Online (план 2) с дополнительный компонент облачных УАТС или Office 365 E5 является обязательным (1).</span><span class="sxs-lookup"><span data-stu-id="9f170-117">To entitle the room with the Enterprise Voice capability so the room can be enabled with a phone number, a Skype for Business Online Plan 2 with the Cloud PBX Add-on or Office 365 E5 is required (1).</span></span>
    
- <span data-ttu-id="9f170-118">Доступность возможности конференц-связи с подключением через ТСОП для конкретного собрания определяется лицензией организатора собрания.</span><span class="sxs-lookup"><span data-stu-id="9f170-118">The availability of PSTN Conferencing entitlement within any given meeting is determined by the license of the meeting organizer.</span></span>
    
- <span data-ttu-id="9f170-119">Лицензия Exchange Online не требуется для учетной записи комнаты Skype, так как эта учетная запись должна настраиваться как учетная запись почтового ящика ресурса.</span><span class="sxs-lookup"><span data-stu-id="9f170-119">An Exchange Online license is not required for the Skype Room account because the account should be configured as a resource mailbox account.</span></span>
    
## <a name="provisioning-overview"></a><span data-ttu-id="9f170-120">Обзор предоставления</span><span class="sxs-lookup"><span data-stu-id="9f170-120">Provisioning overview</span></span>

<span data-ttu-id="9f170-121">Следующая схема Обзор подготовки поток в Office 365 Скайп комнаты системную учетную запись.</span><span class="sxs-lookup"><span data-stu-id="9f170-121">The following diagram provides an overview of the Skype Room System account provisioning flow in Office 365.</span></span>
  
![Этапы подготовки системы для комнаты Skype для O365](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a><span data-ttu-id="9f170-123">Создание новой комнаты переговоров</span><span class="sxs-lookup"><span data-stu-id="9f170-123">Identify a new conference room</span></span>

<span data-ttu-id="9f170-124">Вы уже может быть почтовый ящик ресурса помещения в Exchange, который предоставляет функции планирования или создаваемого почтового ящика ресурса в первый раз упростить развертывание системы Скайп помещений.</span><span class="sxs-lookup"><span data-stu-id="9f170-124">You may already have a resource room mailbox in Exchange that provides the scheduling feature, or you may be creating a resource mailbox for the first time to facilitate Skype Room System deployment.</span></span> <span data-ttu-id="9f170-125">В обоих случаях необходимо создать учетную запись комнаты, которая будет использоваться в клиенте.</span><span class="sxs-lookup"><span data-stu-id="9f170-125">In any case, you must identify a room account to be used in your tenant.</span></span> <span data-ttu-id="9f170-126">Exchange Online подготовки и Скайп для подготовки Business разделов, позволяют для обоих типов учетных записей.</span><span class="sxs-lookup"><span data-stu-id="9f170-126">The Exchange Online Provision and Skype for Business Provision sections provide guidance for both kinds of accounts.</span></span> <span data-ttu-id="9f170-127">Например предположим, у вас есть следующие два комнат, и он хотел развертывания системы Скайп комнаты для их:</span><span class="sxs-lookup"><span data-stu-id="9f170-127">For example, let's say you have the following two rooms, and you would like to deploy Skype Room System for both of them:</span></span>
  
- <span data-ttu-id="9f170-128">Текущая учетная запись почтового ящика ресурсов: confrm1@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="9f170-128">Existing Resource Mailbox Account: confrm1@contoso.onmicrosoft.com</span></span>
    
- <span data-ttu-id="9f170-129">Новая учетная запись почтового ящика ресурсов: confrm2@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="9f170-129">New Resource Mailbox Account: confrm2@contoso.onmicrosoft.com</span></span>
    
## <a name="exchange-online-provisioning"></a><span data-ttu-id="9f170-130">Предоставление Exchange Online</span><span class="sxs-lookup"><span data-stu-id="9f170-130">Exchange Online provisioning</span></span>

<span data-ttu-id="9f170-131">Во-первых подключение к Exchange Online PowerShell, следуя инструкциям, приведенным в разделе [подключение к Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span><span class="sxs-lookup"><span data-stu-id="9f170-131">First, connect to Exchange Online PowerShell by following the instructions in the topic, [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
  
<span data-ttu-id="9f170-132">Чтобы настроить существующую учетную запись почтового ящика ресурса комнаты для системы Скайп помещения, выполните следующие команды в Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="9f170-132">To set an existing resource room mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="9f170-133">Чтобы создать новую учетную запись почтового ящика Exchange ресурсов для системы Скайп помещения, выполните следующие команды в Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="9f170-133">To create a new Exchange resource mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="9f170-134">Предыдущей команды настроить или создать новую учетную запись почтового ящика Exchange ресурсов для использования системы комнаты Скайп посредством включения учетной записи.</span><span class="sxs-lookup"><span data-stu-id="9f170-134">The previous commands set up or create a new Exchange resource mailbox account for Skype Room System usage by enabling the account.</span></span>
  
<span data-ttu-id="9f170-135">После создания почтового ящика, можно использовать командлет Set-CalendarProcessing в Exchange Online PowerShell для настройки почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="9f170-135">After creating the mailbox, you can use the Set-CalendarProcessing cmdlet in Exchange Online PowerShell to configure the mailbox.</span></span> <span data-ttu-id="9f170-136">Дополнительные сведения см. в разделе "Развертывание одного локального леса", шаги 3–6.</span><span class="sxs-lookup"><span data-stu-id="9f170-136">Refer to steps 3 through 6 under Single forest on-premises deployments for more details</span></span>

## <a name="assigning-a-skype-for-business-online-license"></a><span data-ttu-id="9f170-137">Назначение лицензии Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="9f170-137">Assigning a Skype for Business Online license</span></span>

<span data-ttu-id="9f170-138">Теперь можно назначить Скайп для бизнеса Online (план 2) или Скайп для лицензии через Интернет бизнес (план 3) с помощью портала администрирования Office 365, как описано в [Назначение и удаление лицензий на Office 365 для бизнеса](https://support.office.com/en-us/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) или в [Скайп для бизнеса надстройки Лицензирование](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7).</span><span class="sxs-lookup"><span data-stu-id="9f170-138">Now you can assign a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license by using the Office 365 administrative portal as described in [Assign or remove licenses for Office 365 for business](https://support.office.com/en-us/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) or in [Skype for Business add-on licensing](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7).</span></span> 
  
<span data-ttu-id="9f170-139">После назначения лицензии для Скайп для бизнеса в Интернет, вы сможете для входа и убедиться, что учетная запись является активным, с помощью любого Скайп для клиента Business.</span><span class="sxs-lookup"><span data-stu-id="9f170-139">After you assign a license for Skype for Business Online, you will be able to log in and validate that the account is active using any Skype for Business client.</span></span>
  
## <a name="skype-for-business-online-provisioning"></a><span data-ttu-id="9f170-140">Предоставление Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="9f170-140">Skype for Business Online provisioning</span></span>

<span data-ttu-id="9f170-141">После помещения ресурсов почтовый ящик учетной записи была создана и включена, как показано выше, и лицензированных учетной записи для Скайп для бизнеса в Интернет учетной записи будут синхронизироваться с Exchange Online леса для Скайп для бизнеса в Интернет леса с помощью Лес Windows Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9f170-141">After a resource room mailbox account has been created and enabled as shown previously, and you have licensed the account for Skype For Business Online the account will synchronize from the Exchange Online forest to Skype for Business Online forest by using the Windows Azure Active Directory forest.</span></span> <span data-ttu-id="9f170-142">Подготовка Скайп комнаты системную учетную запись в Скайп для бизнеса в Интернет пула необходимы следующие действия.</span><span class="sxs-lookup"><span data-stu-id="9f170-142">The following steps are required to provision the Skype Room System account in the Skype for Business Online pool.</span></span> <span data-ttu-id="9f170-143">Эти шаги совпадают с существующей учетной записи ресурса почтового ящика или учетной записи только что созданный (confrm1 или confrm2), так как после их, необходимо включить в Exchange Online, оба этих учетных записей синхронизация с Скайп для бизнеса в Интернет так же, как:</span><span class="sxs-lookup"><span data-stu-id="9f170-143">These steps are the same for both an existing resource mailbox account or a newly created account (confrm1 or confrm2), because once they are enabled in Exchange Online, both of these accounts will be synchronized to Skype for Business Online in the same way:</span></span>
  
<span data-ttu-id="9f170-144"><<<<<<< Заголовок</span><span class="sxs-lookup"><span data-stu-id="9f170-144"><<<<<<< HEAD</span></span>
1. <span data-ttu-id="9f170-145">Создайте удаленный сеанс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9f170-145">Create a Remote PowerShell session.</span></span> <span data-ttu-id="9f170-146">Обратите внимание, что необходимо загрузить Скайп для бизнес-Online соединителя модуля и Microsoft Online Services помощника по входу и убедитесь в том, что на компьютере настроена.</span><span class="sxs-lookup"><span data-stu-id="9f170-146">Note that you will need to download Skype for Business Online Connector Module and Microsoft Online Services Sign-In Assistant and make sure that your computer is configured.</span></span> <span data-ttu-id="9f170-147">Дополнительные сведения можно [настроить компьютер для Windows PowerShell](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="9f170-147">For more information, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
=======
1. <span data-ttu-id="9f170-148">Создайте удаленный сеанс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9f170-148">Create a Remote PowerShell session.</span></span> <span data-ttu-id="9f170-149">Обратите внимание, что необходимо загрузить Скайп для бизнес-Online соединителя модуля и Microsoft Online Services помощника по входу и убедитесь в том, что на компьютере настроена.</span><span class="sxs-lookup"><span data-stu-id="9f170-149">Note that you will need to download Skype for Business Online Connector Module and Microsoft Online Services Sign-In Assistant and make sure that your computer is configured.</span></span> <span data-ttu-id="9f170-150">Дополнительные сведения можно [настроить компьютер для Windows PowerShell](http://technet.microsoft.com/library/bca143e2-659a-4161-9220-59ffd9fc2874.aspx).</span><span class="sxs-lookup"><span data-stu-id="9f170-150">For more information, see [Set up your computer for Windows PowerShell](http://technet.microsoft.com/library/bca143e2-659a-4161-9220-59ffd9fc2874.aspx).</span></span>
>>>>>>> <span data-ttu-id="9f170-151">0a230b02c47ae4de6638a638b76ed38243c71ab9</span><span class="sxs-lookup"><span data-stu-id="9f170-151">0a230b02c47ae4de6638a638b76ed38243c71ab9</span></span>
    
   ```
   Import-Module LyncOnlineConnector
   $cssess=New-CsOnlineSession -Credential $cred
   Import-PSSession $cssess -AllowClobber
   ```

2. <span data-ttu-id="9f170-152">Чтобы включить учетную запись системы комнаты Скайп для Скайп для бизнеса, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="9f170-152">To enable an Skype Room System account for Skype for Business, run the following command:</span></span>
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    <span data-ttu-id="9f170-153">Вы можете получить RegistrarPool, в котором расположена вашей Скайп для бизнес-пользователей из одного из существующих учетных записей, используя следующую команду, чтобы адрес возвращает этого свойства:</span><span class="sxs-lookup"><span data-stu-id="9f170-153">You can obtain the RegistrarPool address where your Skype for Business users are homed from one of your existing accounts by using the following command to returns this property:</span></span>
    
   ```
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

  
## <a name="password-expiration"></a><span data-ttu-id="9f170-154">Срок действия пароля</span><span class="sxs-lookup"><span data-stu-id="9f170-154">Password expiration</span></span>

<span data-ttu-id="9f170-155">Если не настроить политику истечение срока действия пароля в Office 365, политика срока действия пароля по умолчанию для всех учетных записей пользователей — это 90 дней.</span><span class="sxs-lookup"><span data-stu-id="9f170-155">In Office 365, the default password expiration policy for all of your user accounts is 90 days unless you configure a different password expiration policy.</span></span> <span data-ttu-id="9f170-156">Для Скайп помещений системных учетных записей, можно выбрать пароля неограничен виде с помощью следующих действий.</span><span class="sxs-lookup"><span data-stu-id="9f170-156">For Skype Room System accounts, you can select the Password never expires setting with the following steps.</span></span>
  
1. <span data-ttu-id="9f170-157">Создайте сеанс Windows Azure Active Directory, указав учетные данные глобального администратора клиента.</span><span class="sxs-lookup"><span data-stu-id="9f170-157">Create a Windows Azure Active Directory session by using your tenant global administrator credentials.</span></span>
    
    ```
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. <span data-ttu-id="9f170-158">Набор пароля неограничен параметр для учетной записи системы комнаты Скайп комнаты, созданную ранее с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="9f170-158">Set the Password never expires setting for the Skype Room System room account created previously by using the following command:</span></span>
    
   ```
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

<span data-ttu-id="9f170-159">Дополнительные сведения можно [настроить компьютер для Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="9f170-159">For more information, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  

