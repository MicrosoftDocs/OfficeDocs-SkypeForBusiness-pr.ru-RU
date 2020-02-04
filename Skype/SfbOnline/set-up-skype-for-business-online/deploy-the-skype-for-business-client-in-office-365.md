---
title: Развертывание клиента Skype для бизнеса в среде Office 365
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 8c563b81-22c9-4024-9efe-9fe28c7bbc96
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: 'Learn how to plan and deploy Skype for Business in small, medium, and large organizations and making it available to your users. '
ms.openlocfilehash: 052cc4cb8aa1242628e0f57a57a3fe5532be3d71
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2020
ms.locfileid: "41706504"
---
# <a name="deploy-the-skype-for-business-client-in-office-365"></a><span data-ttu-id="a6cef-103">Развертывание клиента Skype для бизнеса в среде Office 365</span><span class="sxs-lookup"><span data-stu-id="a6cef-103">Deploy the Skype for Business client in Office 365</span></span>

<span data-ttu-id="a6cef-104">В этой статье рассказывается о том, как **[Администратор](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)** может развернуть приложение Skype для бизнеса для людей из вашей организации.</span><span class="sxs-lookup"><span data-stu-id="a6cef-104">This article explains options for how you, the **[admin](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)**, can deploy the Skype for Business app to the people in your organization.</span></span>
  
<span data-ttu-id="a6cef-p101">Перед развертыванием Skype для бизнеса для пользователей убедитесь, что в статье [Настройка Skype для бизнеса Online](set-up-skype-for-business-online.md)выполнена шаги 1-3. Таким образом, приложение Skype для бизнеса будет настроено для вашего домена, у всех пользователей будут лицензии, и вы будете настроены на обмен мгновенными сообщениями и настроили [состояние присутствия в Skype для бизнеса Online](configure-presence-in-skype-for-business-online.md) для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="a6cef-p101">Before you deploy Skype for Business to your users, make sure you've done steps 1-3 in the article [Set up Skype for Business Online](set-up-skype-for-business-online.md). This way, Skype for Business will be set up with your domain, everyone will have their licenses, and you will have configured IM and [Configure presence in Skype for Business Online](configure-presence-in-skype-for-business-online.md) for your organization.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a6cef-p102">Чтобы пользователи могли установить приложение Skype для бизнеса, они должны быть локальными администраторами на компьютере или устройстве. Или они должны входить в локальную группу, которая может устанавливать приложения на своем ПК или устройствах. Если пользователям не разрешено устанавливать программное обеспечение на своих устройствах, вам потребуется установить для них приложение Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="a6cef-p102">For users to install the Skype for Business app, they need to be local admins on their PC or device. Or they will need to be part of a local group that can install apps on their PC or devices. If your users aren't allowed to install software on their devices, you'll need to install the Skype for Business app for them.</span></span> 
  
## <a name="for-most-small-and-medium-sized-businesses"></a><span data-ttu-id="a6cef-110">Для небольших и средних организаций</span><span class="sxs-lookup"><span data-stu-id="a6cef-110">For most small and medium-sized businesses</span></span>

 <span data-ttu-id="a6cef-p103">Пошаговые **инструкции по установке:** Если вы разработали компании малого или среднего бизнеса, мы рекомендуем вам просто попросить пользователей установить приложение Skype для бизнеса на своем ПК. Наведите их на следующие инструкции: [установите Skype для бизнеса](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb). Если они используют Mac, наведите их на раздел [Настройка Lync для Mac 2011 для Office 365](https://support.office.com/article/ae3ebd0e-a1a7-48cf-9350-36b144dc5f88). Приложение Skype для бизнеса устанавливается отдельно от остальных приложений Office.</span><span class="sxs-lookup"><span data-stu-id="a6cef-p103">**Step-by-step installation instructions:** If you have a small or medium-sized business, we recommend that you simply ask your users to install the Skype for Business app on their PC. Point them to these instructions: [Install Skype for Business](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb). If they are using Macs, point them to [Set up Lync for Mac 2011 for Office 365](https://support.office.com/article/ae3ebd0e-a1a7-48cf-9350-36b144dc5f88). The Skype for Business app is installed separately from the rest of the Office apps.</span></span>
  
 <span data-ttu-id="a6cef-115">**Пользователи Office 365 профессиональный плюс.** Если в вашей организации используется план Office 365, который включает Office 365 профессиональный плюс (например, план E3), Skype для бизнеса устанавливается одновременно со скачиванием и установкой приложений Word, Excel, PowerPoint и т. д. Это также означает, что пользователи не могут удалить Skype для бизнеса без удаления всего пакета Office.</span><span class="sxs-lookup"><span data-stu-id="a6cef-115">**Office 365 ProPlus customers:** If your business is using an Office 365 plan that includes Office 365 ProPlus, such as the E3 plan, the Skype for Business app is installed at the same time your users download and install Word, Excel, PowerPoint, etc. This also means they can't uninstall Skype for Business unless they uninstall all of Office.</span></span>
  
### <a name="choose-whether-to-make-skype-for-business-available-to-your-users"></a><span data-ttu-id="a6cef-116">Доступ пользователей к приложению Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="a6cef-116">Choose whether to make Skype for Business available to your users</span></span>

<span data-ttu-id="a6cef-117">[Администратор](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504) может выбрать, будет ли приложение Skype для бизнеса доступно вашим пользователям.</span><span class="sxs-lookup"><span data-stu-id="a6cef-117">As the [admin](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504) you can choose whether to make the Skype for Business app available to your users.</span></span>
  
- <span data-ttu-id="a6cef-118">**Чтобы управлять получением программного обеспечения всеми сотрудниками вашей компании**: Войдите в центр администрирования Microsoft 365, перейдите в раздел **Установка программного обеспечения**, а затем выберите программное обеспечение, которое будет доступно для пользователей.</span><span class="sxs-lookup"><span data-stu-id="a6cef-118">**To control whether everyone in your company gets the software**: Sign in to the Microsoft 365 admin center, go to **Install my software**, and then select the software you want to be available for users.</span></span>
    
    ![Choose the software you want to make available to the people in your company.](../images/5eb9e9d4-6ea2-4cc1-a61d-8a1af5a7c121.png)
  
- <span data-ttu-id="a6cef-120">**Чтобы управлять получением программного обеспечения конкретными сотрудниками вашей компании**, войдите в центр администрирования Microsoft 365, перейдите в раздел **Пользователи** > :**Активные пользователи**, выберите пользователя, которому вы хотите предоставить доступ к программному обеспечению, и нажмите кнопку **изменить** рядом с пунктом **лицензии на продукты** и включите или выключите лицензию.</span><span class="sxs-lookup"><span data-stu-id="a6cef-120">**To control whether specific people in your company get the software**: Sign in to the Microsoft 365 admin center, go to **Users** > **Active users**, select the person who you want to give access to the software, and then click **Edit** next to **Product licenses** and turn the license on or off.</span></span>
    
    ![Choose which software you want the user to access.](../images/91f6f422-2c85-4afd-944f-0021b2f6f109.png)
  
> [!NOTE]
> <span data-ttu-id="a6cef-p104">Если вам нужно узнать, какие планы назначены сотрудникам вашей организации, войдите в центр администрирования Microsoft 365 > **пользователей** > —**Активные пользователи**. Выберите пользователя из списка и просмотрите список лицензии на **продукты**. Если вы используете классический центр администрирования, ознакомьтесь с разделом **назначенная лицензия**.</span><span class="sxs-lookup"><span data-stu-id="a6cef-p104">If you need to see what plans are assigned to people in your organization, sign in to the Microsoft 365 admin center > **Users** > **Active users**. Select the person from the list then look under **Product licenses**. If you are using the classic admin center, look under **Assigned license**.</span></span> 
  
### <a name="manually-deploying-skype-for-business-to-your-users"></a><span data-ttu-id="a6cef-125">Развертывание Skype для бизнеса на компьютерах пользователей вручную</span><span class="sxs-lookup"><span data-stu-id="a6cef-125">Manually deploying Skype for Business to your users</span></span>
<span data-ttu-id="a6cef-126"><a name="bkmk_manual_1"> </a></span><span class="sxs-lookup"><span data-stu-id="a6cef-126"><a name="bkmk_manual_1"> </a></span></span>

<span data-ttu-id="a6cef-p105">Если вы хотите, чтобы пользователи установили приложение Skype для бизнеса из сети, а не из Интернета, вы можете скачать установочные файлы. Для этого перейдите в раздел по **развертыванию программного обеспечения пользователя вручную** в центре администрирования Microsoft 365. Затем вы можете нажать кнопку **установить** и сохранить файл Setup. exe в сетевом расположении.</span><span class="sxs-lookup"><span data-stu-id="a6cef-p105">If you want your users to install the Skype for Business app from a location on your network instead of from the Internet, you can download the setup files. To do this go to the **Manually deploy user software** section of the Microsoft 365 admin center. You can then select **Install** and save the setup .exe file to a network location.</span></span>
  
<span data-ttu-id="a6cef-p106">Кроме того, можно загрузить приложение Skype для бизнеса Basic для пользователей. Вы можете загрузить [Microsoft Skype для бизнеса базовый (32 или 64)](https://www.microsoft.com/download/details.aspx?id=49440).</span><span class="sxs-lookup"><span data-stu-id="a6cef-p106">Another option is to download the Skype for Business Basic app for your users. You can download [Microsoft Skype for Business Basic (32 or 64 Bit)](https://www.microsoft.com/download/details.aspx?id=49440).</span></span>
  
<span data-ttu-id="a6cef-132">После скачивания установочных файлов полной или базовой версии Skype для бизнеса необходимо сообщить пользователям сетевой путь (например, можно отправить ссылку по электронной почте). После этого пользователи смогут перейти туда и запустить установочный файл, чтобы установить продукт на своем компьютере.</span><span class="sxs-lookup"><span data-stu-id="a6cef-132">For both the full and basic Skype for Business apps, after you have downloaded the setup files, you will need to manually send (for example, in email) the network path to the users so they can run the setup program to install the app on their computer.</span></span>
  
<span data-ttu-id="a6cef-133">Загруженные файлы также можно использовать для установки приложения Skype для бизнеса на компьютерах пользователей с помощью имеющихся инструментов и процессов развертывания.</span><span class="sxs-lookup"><span data-stu-id="a6cef-133">You can also use these downloads to deploy the Skype for Business app to your users by using your existing software deployment tools and processes.</span></span>
  
## <a name="for-larger-and-enterprise-organizations"></a><span data-ttu-id="a6cef-134">Для крупных организаций и предприятий</span><span class="sxs-lookup"><span data-stu-id="a6cef-134">For larger and enterprise organizations</span></span>

> [!NOTE]
> <span data-ttu-id="a6cef-p107">Этот раздел относится только к приложению Skype для бизнеса, доступному в планах Office 365. Если в вашей организации используется корпоративная версия приложения Skype для бизнеса, созданная с помощью установщика Windows (MSI), ознакомьтесь с [Разстройкой установки клиента Windows в Skype для бизнеса Server](https://technet.microsoft.com/library/jj204934.aspx).</span><span class="sxs-lookup"><span data-stu-id="a6cef-p107">This section only applies to the Skype for Business app available through Office 365 plans. If your organization is using a volume licensed version of the Skype for Business app, which is Windows Installer-based (MSI), see [Customize Windows client installation in Skype for Business Server](https://technet.microsoft.com/library/jj204934.aspx).</span></span>
  
<span data-ttu-id="a6cef-p108">Во многих крупных организациях и на предприятиях пользователям запрещено самостоятельно устанавливать программное обеспечение на своих компьютерах. Необходимое программное обеспечение устанавливается сотрудниками ИТ-отдела. ИТ-отделам может потребоваться возможность контролировать объем интернет-трафика или потребление ресурсов полосы пропускания, поэтому они могут установить приложение с ближайшего сетевого ресурса, а не через Интернет или корпоративную сеть.</span><span class="sxs-lookup"><span data-stu-id="a6cef-p108">In many enterprises or large organizations, users aren't allowed to install software on their computers. Instead, the IT departments deploy the necessary software to the users' computers. IT departments also might want to control the amount of Internet or network bandwidth used in their organization, so they want to install software from a nearby location on their network instead of from across the Internet or across the corporate network.</span></span>
  
<span data-ttu-id="a6cef-p109">С помощью Office 365 у вас есть несколько вариантов развертывания приложения Skype для бизнеса, если вы хотите указать, откуда оно установлено. Ниже указаны некоторые из этих параметров.</span><span class="sxs-lookup"><span data-stu-id="a6cef-p109">With Office 365, you have several options for deploying the Skype for Business app if you want to control where it's installed from. Some of those options include the following:</span></span>
  
- <span data-ttu-id="a6cef-142">Скачайте приложение Skype для бизнеса в локальную сеть из центра администрирования Microsoft 365, как описано в разделе [развертывание Skype для бизнеса для пользователей вручную](deploy-the-skype-for-business-client-in-office-365.md#bkmk_manual_1).</span><span class="sxs-lookup"><span data-stu-id="a6cef-142">Download the Skype for Business app to your local network from the Microsoft 365 admin center, as described in [Manually deploying Skype for Business to your users](deploy-the-skype-for-business-client-in-office-365.md#bkmk_manual_1).</span></span>
    
- <span data-ttu-id="a6cef-p110">Использование **[средства развертывания Office](https://go.microsoft.com/fwlink/p/?LinkID=626065)** для загрузки Office 365 ProPlus или приложения Skype для бизнеса в локальную сеть. Затем приложение можно развернуть на компьютерах пользователей с помощью средства развертывания Office. Средство развертывания Office позволяет контролировать определенные аспекты развертывания, такие как язык и версия (32-разрядная или 64-разрядная).</span><span class="sxs-lookup"><span data-stu-id="a6cef-p110">Use the **[Office Deployment Tool](https://go.microsoft.com/fwlink/p/?LinkID=626065)** to download either Office 365 ProPlus or the Skype for Business app to your local network. Then, use the Office Deployment Tool to deploy the app to your users. The Office Deployment Tool gives you the ability to control certain aspects of the deployment, such as languages and version (32-bit or 64-bit).</span></span>
    
- <span data-ttu-id="a6cef-p111">С помощью существующих средств и процессов развертывания программного обеспечения, таких как Microsoft Endpoint Configuration Manager, вы можете развернуть Office 365 профессиональный плюс или приложение Skype для бизнеса для пользователей. Вы можете использовать существующие инструменты и процессы с помощью [средства развертывания Office](https://go.microsoft.com/fwlink/p/?LinkID=626065) или программного обеспечения, которое вы загрузили в центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a6cef-p111">Use your existing software deployment tools and processes, such as Microsoft Endpoint Configuration Manager, to deploy Office 365 ProPlus or the Skype for Business app to your users. You can use your existing tools and processes with the [Office Deployment Tool](https://go.microsoft.com/fwlink/p/?LinkID=626065) or with the software that you've downloaded from the Microsoft 365 admin center.</span></span>
    
### <a name="more-info-on-using-the-office-deployment-tool"></a><span data-ttu-id="a6cef-148">Дополнительная информация об использовании средства развертывания Office</span><span class="sxs-lookup"><span data-stu-id="a6cef-148">More info on using the Office Deployment Tool</span></span>

<span data-ttu-id="a6cef-149">Подробнее о загрузке средства развертывания Office и дополнительных сведениях о том, как установить приложение Skype для бизнеса и другие клиентские приложения Office 365, можно найти [в разделе Управление параметрами загрузки программного обеспечения в office 365](https://support.office.com/article/c13051e6-f75c-4737-bc0d-7685dcedf360).</span><span class="sxs-lookup"><span data-stu-id="a6cef-149">For details on downloading the Office Deployment Tool and more information on installing the Skype for Business app and other Office 365 client apps, see [Manage software download settings in Office 365](https://support.office.com/article/c13051e6-f75c-4737-bc0d-7685dcedf360).</span></span>
  
<span data-ttu-id="a6cef-150">Ниже описаны действия, которые необходимо выполнить для развертывания приложения с помощью средства развертывания Office.</span><span class="sxs-lookup"><span data-stu-id="a6cef-150">Here's an overview of the steps involved in using the Office Deployment Tool to deploy an app:</span></span>
  
1. <span data-ttu-id="a6cef-151">**[Загрузите последнюю версию средства развертывания Office](https://www.microsoft.com/download/details.aspx?id=49117)** из Центра загрузки Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a6cef-151">**[Download the newest Office Deployment Tool](https://www.microsoft.com/download/details.aspx?id=49117)** from the Microsoft Download Center.</span></span>
    
2. <span data-ttu-id="a6cef-152">Создайте файл конфигурации configuration.xml, который будет использоваться инструментом средством развертывания Office. Этот файл должен содержать параметры установки клиентского приложения, например версию (32-разрядная или 64-разрядная), язык установки и т. д.</span><span class="sxs-lookup"><span data-stu-id="a6cef-152">Create the configuration.xml file to be used with the Office Deployment Tool that has the client app settings you want, such as setting the version (32-bit or 64-bit), the installation language, etc.</span></span>
    
3. <span data-ttu-id="a6cef-153">С помощью средства развертывания Office и файла configuration.xml скачайте установочные файлы на локальный или сетевой ресурс из сети доставки содержимого Office (CDN).</span><span class="sxs-lookup"><span data-stu-id="a6cef-153">Use the Office Deployment Tool and the configuration.xml file to download the setup files to your local or internal network from the Office Content Delivery Network (CDN).</span></span>
    
4. <span data-ttu-id="a6cef-154">C помощью средства развертывания Office и файла configuration.xml установите клиентские приложения Office, включая Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="a6cef-154">Use Office Deployment Tool and the configuration.xml to install the Office client apps, including the Skype for Business app.</span></span>
    
<span data-ttu-id="a6cef-155">Подробную информацию о средстве развертывания Office и файле configuration.xml см. в следующих статьях.</span><span class="sxs-lookup"><span data-stu-id="a6cef-155">For details on using the Office Deployment Tool and configuration.xml file, see the following articles:</span></span>
  
- [<span data-ttu-id="a6cef-156">Основные сведения о средстве развертывания Office</span><span class="sxs-lookup"><span data-stu-id="a6cef-156">Office Deployment Tool overview</span></span>](https://technet.microsoft.com/library/jj219422.aspx)
    
- [<span data-ttu-id="a6cef-157">Параметры файла configuration.xml</span><span class="sxs-lookup"><span data-stu-id="a6cef-157">Configuration.xml settings</span></span>](https://technet.microsoft.com/library/jj219426.aspx)
    
### <a name="more-info-on-using-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="a6cef-158">Дополнительные сведения об использовании диспетчера конфигурации конечных точек Майкрософт</span><span class="sxs-lookup"><span data-stu-id="a6cef-158">More info on using Microsoft Endpoint Configuration Manager</span></span>

<span data-ttu-id="a6cef-p112">Вы можете развернуть приложение Skype для бизнеса с помощью существующих средств и процессов развертывания программного обеспечения, таких как Microsoft Endpoint Configuration Manager. Вы можете использовать эти средства и процессы вместе с программным обеспечением, которое вы скачиваете из центра администрирования Microsoft 365 или с помощью средства развертывания Office.</span><span class="sxs-lookup"><span data-stu-id="a6cef-p112">You can use your existing software deployment tools and processes, such as Microsoft Endpoint Configuration Manager, to deploy the Skype for Business app. You can use these tools and processes with either the software that you download from the Microsoft 365 admin center or with the Office Deployment Tool.</span></span>
  
<span data-ttu-id="a6cef-161">Дополнительные сведения об использовании Configuration Manager для развертывания программного обеспечения см. в следующих статьях.</span><span class="sxs-lookup"><span data-stu-id="a6cef-161">For more information about using Configuration Manager to deploy software, see the following articles:</span></span>
  
- [<span data-ttu-id="a6cef-162">Создание приложений в Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="a6cef-162">Create applications in Configuration Manager</span></span>](https://docs.microsoft.com/configmgr/apps/deploy-use/create-applications)
    
- [<span data-ttu-id="a6cef-163">Развертывание приложений с помощью Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="a6cef-163">Deploy applications with Configuration Manager</span></span>](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-applications)
    
<span data-ttu-id="a6cef-164">Если вы разворачиваете приложение Skype для бизнеса в рамках развертывания Office 365 ProPlus, ознакомьтесь с разметкой [Управление office 365 профессиональный плюс с помощью Configuration Manager](https://docs.microsoft.com/configmgr/sum/deploy-use/manage-office-365-proplus-updates).</span><span class="sxs-lookup"><span data-stu-id="a6cef-164">If you're deploying the Skype for Business app as part of deploying Office 365 ProPlus, see [Manage Office 365 ProPlus with Configuration Manager](https://docs.microsoft.com/configmgr/sum/deploy-use/manage-office-365-proplus-updates).</span></span>
  
## <a name="planning-for-updates-to-the-skype-for-business-app"></a><span data-ttu-id="a6cef-165">Планирование обновлений приложения Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="a6cef-165">Planning for updates to the Skype for Business app</span></span>

<span data-ttu-id="a6cef-p113">При развертывании приложения Skype для бизнеса необходимо выбрать способ получения обновлений после установки приложения Skype для бизнеса. Обновления могут включать новые функции, улучшения системы безопасности и прочие исправления и улучшения, повышающие стабильность или производительность приложения. Необходимо определить два основных параметра:</span><span class="sxs-lookup"><span data-stu-id="a6cef-p113">As part of deploying the Skype for Business app, you need to consider how you want to get updates after Skype for Business is installed. These updates can include new features, security updates, or non-security updates, such as updates that provide stability or performance improvements. The two primary things you need to consider are :</span></span>
  
- <span data-ttu-id="a6cef-169">Источник обновлений</span><span class="sxs-lookup"><span data-stu-id="a6cef-169">Where do you want to get updates from</span></span>
    
- <span data-ttu-id="a6cef-170">Периодичность получения обновлений</span><span class="sxs-lookup"><span data-stu-id="a6cef-170">How often do you want to get feature updates</span></span>
    
<span data-ttu-id="a6cef-171">Можно выбрать источник обновлений функциональности и периодичность их получения, но нельзя выбрать определенные обновления системы безопасности и прочие обновления.</span><span class="sxs-lookup"><span data-stu-id="a6cef-171">While you can control where you get updates from and how often you get feature updates, you can't choose which specific security updates or non-security updates you get.</span></span>
  
 <span data-ttu-id="a6cef-172">**Источник обновлений**</span><span class="sxs-lookup"><span data-stu-id="a6cef-172">**Where to get updates from**</span></span>
  
<span data-ttu-id="a6cef-p114">По умолчанию после установки приложения Skype для бизнеса обновления автоматически загружаются через Интернет сразу после их появления. Если вам необходим дополнительный контроль над периодичностью обновлений или источником их установки, настройте эти параметры с помощью средства развертывания Office или групповой политики.</span><span class="sxs-lookup"><span data-stu-id="a6cef-p114">By default, after the Skype for Business app is installed, updates will be automatically downloaded from the Internet when they are available from Microsoft. If you want more control over when updates occur or where the updates are installed from, you can use the Office Deployment Tool or Group Policy to configure that.</span></span>
  
<span data-ttu-id="a6cef-p115">Например, многие организации предпочитают предварительно тестировать обновления на группе пользователей, прежде чем устанавливать их для всех пользователей организации. Это можно сделать с помощью средства развертывания Office или групповой политики. Вместо автоматической загрузки обновлений через Интернет можно настроить получение обновлений для приложения Skype для бизнеса с определенного сетевого ресурса. Затем с помощью средства развертывания Office можно ежемесячно загружать обновления в локальную сеть.</span><span class="sxs-lookup"><span data-stu-id="a6cef-p115">For example, many organizations want to test updates with a group of users before deploying them throughout the organization. You can do this by using the Office Deployment Tool or Group Policy to configure the Skype for Business app to get updates from a specific location on your network, instead of automatically from the Internet. Then, you can use the Office Deployment Tool to download the updates every month to your local network.</span></span>
  
<span data-ttu-id="a6cef-178">Дополнительные сведения об обновлениях программного обеспечения Office 365 см. в следующих статьях.</span><span class="sxs-lookup"><span data-stu-id="a6cef-178">For more information about how updates work for Office 365 software, see these articles:</span></span>
  
- [<span data-ttu-id="a6cef-179">Общие сведения об обновлении Office 365 профессиональный плюс</span><span class="sxs-lookup"><span data-stu-id="a6cef-179">Overview of the update process for Office 365 ProPlus</span></span>](https://technet.microsoft.com/library/dn761709.aspx)
    
- [<span data-ttu-id="a6cef-180">Выбор способа управления обновлениями в Office 365 профессиональный плюс</span><span class="sxs-lookup"><span data-stu-id="a6cef-180">Choose how to manage updates to Office 365 ProPlus</span></span>](https://technet.microsoft.com/library/dn761707.aspx)
    
- [<span data-ttu-id="a6cef-181">Настройка параметров обновлений для Office 365 профессиональный плюс</span><span class="sxs-lookup"><span data-stu-id="a6cef-181">Configure update settings for Office 365 ProPlus</span></span>](https://technet.microsoft.com/library/dn761708.aspx)
    
  <span data-ttu-id="a6cef-182">**Периодичность получения обновлений функциональности**</span><span class="sxs-lookup"><span data-stu-id="a6cef-182">**How often to get feature updates**</span></span>
  
<span data-ttu-id="a6cef-p116">Помимо источника обновлений также можно настроить периодичность обновления функциональности клиента Skype для бизнеса. Существует два возможных варианта:</span><span class="sxs-lookup"><span data-stu-id="a6cef-p116">In addition to where you get updates from, you can also control how often you get new features for the Skype for Business client. The two choices are the following:</span></span>
  
- <span data-ttu-id="a6cef-185">Ежемесячное получение обновлений при появлении новых функций</span><span class="sxs-lookup"><span data-stu-id="a6cef-185">Get feature updates every month, if there are new features</span></span>
    
- <span data-ttu-id="a6cef-186">Получение обновлений функциональности раз в полгода</span><span class="sxs-lookup"><span data-stu-id="a6cef-186">Get features updates every six months</span></span>
    
<span data-ttu-id="a6cef-187">Если организации необходимо протестировать новые функции, она может устанавливать обновления два раза в год, а не каждый месяц.</span><span class="sxs-lookup"><span data-stu-id="a6cef-187">For some organizations, they want time to test new features, so they want to get feature updates only twice a year instead of every month.</span></span>
  
<span data-ttu-id="a6cef-p117">Настроить периодичность обновления функциональности и канал обновлений можно с помощью средства развертывания Office или с помощью групповой политики. Параметр "Ежемесячный канал" позволяет получать обновления ежемесячно (приблизительно), а параметр "Полугодовой канал" позволяет получать обновления раз в полгода. Дополнительные сведения о каналах см. в статье [Общие сведения о каналах обновлений для Office 365 профессиональный плюс](https://support.office.com/article/9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4).</span><span class="sxs-lookup"><span data-stu-id="a6cef-p117">You can control how often you get feature updates by using the Office Deployment Tool or Group Policy to configure the update channel. The Monthly Channel gives you feature updates monthly (approximately), while the Semi-Annual Channel gives you feature updates every six months. For more information about channels, see [Overview of update channels for Office 365 ProPlus](https://support.office.com/article/9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="a6cef-191">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="a6cef-191">Related topics</span></span>

[<span data-ttu-id="a6cef-192">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="a6cef-192">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)
  
[<span data-ttu-id="a6cef-193">Лицензирование надстроек Skype для бизнеса и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a6cef-193">Skype for Business and Microsoft Teams add-on licensing</span></span>](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
 
