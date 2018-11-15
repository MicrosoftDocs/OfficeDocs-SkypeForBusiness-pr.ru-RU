---
title: Предоставление учетных записей системы комнат Skype в Office 365
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c36150bb-461c-4f1c-877b-fac7fb232f7c
description: В этом разделе описывается выделение учетных записей системы комнат Skype в Office 365.
ms.openlocfilehash: a1b24e25236f221d280631efd83c0e83b7ae44f2
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2018
ms.locfileid: "26532765"
---
# <a name="provisioning-skype-room-system-accounts-in-office-365"></a><span data-ttu-id="75d22-103">Предоставление учетных записей системы комнат Skype в Office 365</span><span class="sxs-lookup"><span data-stu-id="75d22-103">Provisioning Skype Room System accounts in Office 365</span></span>
 
<span data-ttu-id="75d22-104">В этом разделе описывается выделение учетных записей системы комнат Skype в Office 365.</span><span class="sxs-lookup"><span data-stu-id="75d22-104">Read this topic to learn about provisioning Skype Room System accounts in Office 365.</span></span>
  
<span data-ttu-id="75d22-105">В данном разделе рассматриваются Скайп комнаты системной учетной записью, подготовки для клиента Office 365.</span><span class="sxs-lookup"><span data-stu-id="75d22-105">The following section covers Skype Room System account provisioning for an Office 365 tenant.</span></span>
  
## <a name="office-365-prerequisites"></a><span data-ttu-id="75d22-106">Предварительные требования для Office 365</span><span class="sxs-lookup"><span data-stu-id="75d22-106">Office 365 prerequisites</span></span>

<span data-ttu-id="75d22-107">Сетевой клиент должен удовлетворять следующим требованиям:</span><span class="sxs-lookup"><span data-stu-id="75d22-107">Your online tenant must meet the following requirements:</span></span>
  
- <span data-ttu-id="75d22-108">План Office 365 необходимо включить Скайп для бизнеса Online план 2, или Office 365 E1, E3 или E5.</span><span class="sxs-lookup"><span data-stu-id="75d22-108">The Office 365 plan must include Skype for Business Online Plan 2, or Office 365 E1, E3 or E5.</span></span> <br/><span data-ttu-id="75d22-109">Дополнительные сведения о Скайп для бизнеса Online планы см [Скайп для описания службы Online бизнеса](https://technet.microsoft.com/library/jj822172.aspx).</span><span class="sxs-lookup"><span data-stu-id="75d22-109">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span></span>
    
- <span data-ttu-id="75d22-110">Клиент должен иметь возможности конференц-связи Скайп для бизнеса включен.</span><span class="sxs-lookup"><span data-stu-id="75d22-110">Your tenant must have the conferencing capability of Skype for Business enabled.</span></span>
    
- <span data-ttu-id="75d22-111">У пользователя должно быть включено приложение Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="75d22-111">Your tenant must have Exchange Online enabled.</span></span> 
    
- <span data-ttu-id="75d22-112">Удаленный администратор пользователя должен иметь следующие права доступа PowerShell:</span><span class="sxs-lookup"><span data-stu-id="75d22-112">Your tenant remote administrator must have the following PowerShell access:</span></span>
    
  - <span data-ttu-id="75d22-113">Удаленный доступ PowerShell к Exchange</span><span class="sxs-lookup"><span data-stu-id="75d22-113">Exchange Remote PowerShell access</span></span>
    
  - <span data-ttu-id="75d22-114">Скайп для доступа к Business Online удаленной оболочки PowerShell</span><span class="sxs-lookup"><span data-stu-id="75d22-114">Skype for Business Online Remote PowerShell access</span></span>
    
  - <span data-ttu-id="75d22-115">Windows Azure модуль Active Directory для Windows PowerShell для доступа к Office 365 доступ к каталогу</span><span class="sxs-lookup"><span data-stu-id="75d22-115">Windows Azure Active Directory Module for Windows PowerShell to access Office 365 directory access</span></span>
    
<span data-ttu-id="75d22-116">Для учетной записи комнаты Skype необходимы следующие лицензии::</span><span class="sxs-lookup"><span data-stu-id="75d22-116">For the Skype Room account, the following licensing is required:</span></span>
  
- <span data-ttu-id="75d22-117">Скайп для бизнеса Online (план 2) или Office 365 E1 или E3 лицензия требуется для включения Скайп собрания.</span><span class="sxs-lookup"><span data-stu-id="75d22-117">A Skype for Business Online Plan 2 or Office 365 E1 or E3 license is required to enable Skype Meetings.</span></span>
    
- <span data-ttu-id="75d22-118">Для предоставления комнаты с возможностью корпоративной голосовой связи, поэтому комнаты можно включить с номером телефона, Скайп для бизнеса Online (план 2) с телефонной системой лицензии или Office 365 E5 является обязательным (1).</span><span class="sxs-lookup"><span data-stu-id="75d22-118">To entitle the room with the Enterprise Voice capability so the room can be enabled with a phone number, a Skype for Business Online Plan 2 with the Phone System license or Office 365 E5 is required (1).</span></span>
    
- <span data-ttu-id="75d22-119">Если вам требуется-связь с возможностями собрания, необходимо будет аудиоконференций и лицензии телефонной системой.</span><span class="sxs-lookup"><span data-stu-id="75d22-119">If you need dial-in capabilities from a meeting, you will need an audio conferencing and Phone System license.</span></span>  <span data-ttu-id="75d22-120">Если вам требуется подключение по телефонной линии возможности из собрания, необходимо будет внутри страны или внутреннее и международное вызов план.</span><span class="sxs-lookup"><span data-stu-id="75d22-120">If you need dial-out capabilities from a meeting, you will need a domestic or domestic and international Calling Plan.</span></span> 
    
- <span data-ttu-id="75d22-121">Лицензия Exchange Online не требуется для учетной записи комнаты Skype, так как эта учетная запись должна настраиваться как учетная запись почтового ящика ресурса.</span><span class="sxs-lookup"><span data-stu-id="75d22-121">An Exchange Online license is not required for the Skype Room account because the account should be configured as a resource mailbox account.</span></span>
    
## <a name="provisioning-overview"></a><span data-ttu-id="75d22-122">Обзор предоставления</span><span class="sxs-lookup"><span data-stu-id="75d22-122">Provisioning overview</span></span>

<span data-ttu-id="75d22-123">Следующая схема Обзор подготовки поток в Office 365 Скайп комнаты системную учетную запись.</span><span class="sxs-lookup"><span data-stu-id="75d22-123">The following diagram provides an overview of the Skype Room System account provisioning flow in Office 365.</span></span>
  
![Этапы подготовки системы для комнаты Skype для O365](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a><span data-ttu-id="75d22-125">Создание новой комнаты переговоров</span><span class="sxs-lookup"><span data-stu-id="75d22-125">Identify a new conference room</span></span>

<span data-ttu-id="75d22-126">Вы уже может быть почтовый ящик ресурса помещения в Exchange, который предоставляет функции планирования или создаваемого почтового ящика ресурса в первый раз упростить развертывание системы Скайп помещений.</span><span class="sxs-lookup"><span data-stu-id="75d22-126">You may already have a resource room mailbox in Exchange that provides the scheduling feature, or you may be creating a resource mailbox for the first time to facilitate Skype Room System deployment.</span></span> <span data-ttu-id="75d22-127">В обоих случаях необходимо создать учетную запись комнаты, которая будет использоваться в клиенте.</span><span class="sxs-lookup"><span data-stu-id="75d22-127">In any case, you must identify a room account to be used in your tenant.</span></span> <span data-ttu-id="75d22-128">Exchange Online подготовки и Скайп для подготовки Business разделов, позволяют для обоих типов учетных записей.</span><span class="sxs-lookup"><span data-stu-id="75d22-128">The Exchange Online Provision and Skype for Business Provision sections provide guidance for both kinds of accounts.</span></span> <span data-ttu-id="75d22-129">Например предположим, у вас есть следующие два комнат, и он хотел развертывания системы Скайп комнаты для их:</span><span class="sxs-lookup"><span data-stu-id="75d22-129">For example, let's say you have the following two rooms, and you would like to deploy Skype Room System for both of them:</span></span>
  
- <span data-ttu-id="75d22-130">Текущая учетная запись почтового ящика ресурсов: confrm1@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="75d22-130">Existing Resource Mailbox Account: confrm1@contoso.onmicrosoft.com</span></span>
    
- <span data-ttu-id="75d22-131">Новая учетная запись почтового ящика ресурсов: confrm2@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="75d22-131">New Resource Mailbox Account: confrm2@contoso.onmicrosoft.com</span></span>
    
## <a name="exchange-online-provisioning"></a><span data-ttu-id="75d22-132">Предоставление Exchange Online</span><span class="sxs-lookup"><span data-stu-id="75d22-132">Exchange Online provisioning</span></span>

<span data-ttu-id="75d22-133">Во-первых подключение к Exchange Online PowerShell, следуя инструкциям, приведенным в разделе [подключение к Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span><span class="sxs-lookup"><span data-stu-id="75d22-133">First, connect to Exchange Online PowerShell by following the instructions in the topic, [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
  
<span data-ttu-id="75d22-134">Чтобы настроить существующую учетную запись почтового ящика ресурса комнаты для системы Скайп помещения, выполните следующие команды в Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="75d22-134">To set an existing resource room mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="75d22-135">Чтобы создать новую учетную запись почтового ящика Exchange ресурсов для системы Скайп помещения, выполните следующие команды в Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="75d22-135">To create a new Exchange resource mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="75d22-136">Предыдущей команды настроить или создать новую учетную запись почтового ящика Exchange ресурсов для использования системы комнаты Скайп посредством включения учетной записи.</span><span class="sxs-lookup"><span data-stu-id="75d22-136">The previous commands set up or create a new Exchange resource mailbox account for Skype Room System usage by enabling the account.</span></span>
  
<span data-ttu-id="75d22-137">После создания почтового ящика, можно использовать командлет Set-CalendarProcessing в Exchange Online PowerShell для настройки почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="75d22-137">After creating the mailbox, you can use the Set-CalendarProcessing cmdlet in Exchange Online PowerShell to configure the mailbox.</span></span> <span data-ttu-id="75d22-138">Дополнительные сведения см. в разделе "Развертывание одного локального леса", шаги 3–6.</span><span class="sxs-lookup"><span data-stu-id="75d22-138">Refer to steps 3 through 6 under Single forest on-premises deployments for more details</span></span>

## <a name="assigning-a-skype-for-business-online-license"></a><span data-ttu-id="75d22-139">Назначение лицензии Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="75d22-139">Assigning a Skype for Business Online license</span></span>

<span data-ttu-id="75d22-140">Теперь можно назначить Скайп для бизнеса Online (план 2) или Скайп для лицензии через Интернет бизнес (план 3) с помощью портала администрирования Office 365, как описано в [Назначение и удаление лицензий на Office 365 для бизнеса](https://support.office.com/en-us/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) или в [Скайп для бизнеса надстройки Лицензирование](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7).</span><span class="sxs-lookup"><span data-stu-id="75d22-140">Now you can assign a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license by using the Office 365 administrative portal as described in [Assign or remove licenses for Office 365 for business](https://support.office.com/en-us/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) or in [Skype for Business add-on licensing](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7).</span></span> 
  
<span data-ttu-id="75d22-141">После назначения лицензии для Скайп для бизнеса в Интернет, вы сможете для входа и убедиться, что учетная запись является активным, с помощью любого Скайп для клиента Business.</span><span class="sxs-lookup"><span data-stu-id="75d22-141">After you assign a license for Skype for Business Online, you will be able to log in and validate that the account is active using any Skype for Business client.</span></span>
  
## <a name="skype-for-business-online-provisioning"></a><span data-ttu-id="75d22-142">Предоставление Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="75d22-142">Skype for Business Online provisioning</span></span>

<span data-ttu-id="75d22-143">После помещения ресурсов почтовый ящик учетной записи была создана и включена, как показано выше, и лицензированных учетной записи для Скайп для бизнеса в Интернет учетной записи будут синхронизироваться с Exchange Online леса для Скайп для бизнеса в Интернет леса с помощью Лес Windows Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="75d22-143">After a resource room mailbox account has been created and enabled as shown previously, and you have licensed the account for Skype For Business Online the account will synchronize from the Exchange Online forest to Skype for Business Online forest by using the Windows Azure Active Directory forest.</span></span> <span data-ttu-id="75d22-144">Подготовка Скайп комнаты системную учетную запись в Скайп для бизнеса в Интернет пула необходимы следующие действия.</span><span class="sxs-lookup"><span data-stu-id="75d22-144">The following steps are required to provision the Skype Room System account in the Skype for Business Online pool.</span></span> <span data-ttu-id="75d22-145">Эти шаги совпадают с существующей учетной записи ресурса почтового ящика или учетной записи только что созданный (confrm1 или confrm2), так как после их, необходимо включить в Exchange Online, оба этих учетных записей синхронизация с Скайп для бизнеса в Интернет так же, как:</span><span class="sxs-lookup"><span data-stu-id="75d22-145">These steps are the same for both an existing resource mailbox account or a newly created account (confrm1 or confrm2), because once they are enabled in Exchange Online, both of these accounts will be synchronized to Skype for Business Online in the same way:</span></span>
  
1. <span data-ttu-id="75d22-146">Создайте удаленный сеанс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="75d22-146">Create a Remote PowerShell session.</span></span> <span data-ttu-id="75d22-147">Обратите внимание, что необходимо загрузить Скайп для бизнес-Online соединителя модуля и Microsoft Online Services помощника по входу и убедитесь в том, что на компьютере настроена.</span><span class="sxs-lookup"><span data-stu-id="75d22-147">Note that you will need to download Skype for Business Online Connector Module and Microsoft Online Services Sign-In Assistant and make sure that your computer is configured.</span></span> <span data-ttu-id="75d22-148">Дополнительные сведения можно [настроить компьютер для Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="75d22-148">For more information, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
    
   ```
   Import-Module LyncOnlineConnector
   $cssess=New-CsOnlineSession -Credential $cred
   Import-PSSession $cssess -AllowClobber
   ```

2. <span data-ttu-id="75d22-149">Чтобы включить учетную запись системы комнаты Скайп для Скайп для бизнеса, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="75d22-149">To enable an Skype Room System account for Skype for Business, run the following command:</span></span>
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    <span data-ttu-id="75d22-150">Вы можете получить RegistrarPool, в котором расположена вашей Скайп для бизнес-пользователей из одного из существующих учетных записей, используя следующую команду, чтобы адрес возвращает этого свойства:</span><span class="sxs-lookup"><span data-stu-id="75d22-150">You can obtain the RegistrarPool address where your Skype for Business users are homed from one of your existing accounts by using the following command to returns this property:</span></span>
    
   ```
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

  
## <a name="password-expiration"></a><span data-ttu-id="75d22-151">Срок действия пароля</span><span class="sxs-lookup"><span data-stu-id="75d22-151">Password expiration</span></span>

<span data-ttu-id="75d22-152">Если не настроить политику истечение срока действия пароля в Office 365, политика срока действия пароля по умолчанию для всех учетных записей пользователей — это 90 дней.</span><span class="sxs-lookup"><span data-stu-id="75d22-152">In Office 365, the default password expiration policy for all of your user accounts is 90 days unless you configure a different password expiration policy.</span></span> <span data-ttu-id="75d22-153">Для Скайп помещений системных учетных записей, можно выбрать пароля неограничен виде с помощью следующих действий.</span><span class="sxs-lookup"><span data-stu-id="75d22-153">For Skype Room System accounts, you can select the Password never expires setting with the following steps.</span></span>
  
1. <span data-ttu-id="75d22-154">Создайте сеанс Windows Azure Active Directory, указав учетные данные глобального администратора клиента.</span><span class="sxs-lookup"><span data-stu-id="75d22-154">Create a Windows Azure Active Directory session by using your tenant global administrator credentials.</span></span>
    
    ```
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. <span data-ttu-id="75d22-155">Набор пароля неограничен параметр для учетной записи системы комнаты Скайп комнаты, созданную ранее с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="75d22-155">Set the Password never expires setting for the Skype Room System room account created previously by using the following command:</span></span>
    
   ```
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

<span data-ttu-id="75d22-156">Дополнительные сведения можно [настроить компьютер для Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="75d22-156">For more information, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  
## <a name="validate"></a><span data-ttu-id="75d22-157">Проверка</span><span class="sxs-lookup"><span data-stu-id="75d22-157">Validate</span></span>

<span data-ttu-id="75d22-158">Для проверки можно использовать любой Скайп для бизнеса клиента для входа в учетную запись, которую вы создали.</span><span class="sxs-lookup"><span data-stu-id="75d22-158">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>

