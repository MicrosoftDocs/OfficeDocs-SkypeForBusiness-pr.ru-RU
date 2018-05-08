---
title: Процесс развертывания приложения "Объявления" в Skype для бизнеса Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
description: Процесс развертывания и действия для объявлений приложения в Скайп Business Server корпоративной голосовой связи.
ms.openlocfilehash: 08a52569dede43bbe54b1bf7e62f37114ba68853
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="deployment-process-for-the-announcement-application-in-skype-for-business-server-2015"></a><span data-ttu-id="14440-103">Процесс развертывания приложения "Объявления" в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="14440-103">Deployment process for the Announcement application in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="14440-104">Процесс развертывания и действия для объявлений приложения в Скайп Business Server корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="14440-104">Deployment process and steps for Announcement application in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="14440-105">Объявление приложения — это функция корпоративной голосовой связи, которая позволяет настроить, что происходит с вызовы неназначенных extensions (расширения, которые являются допустимыми для вашей организации, но не назначенные человека или телефон).</span><span class="sxs-lookup"><span data-stu-id="14440-105">The Announcement application is an Enterprise Voice feature that enables you to configure what happens to calls to unassigned extensions (extensions that are valid for your organization, but are not assigned to a person or a phone).</span></span> <span data-ttu-id="14440-106">Например, можно настроить эту функцию таким образом, чтобы при выполнении вызовов на неприсвоенные номера воспроизводилось сообщение и/или эти вызовы передавались на другое назначение.</span><span class="sxs-lookup"><span data-stu-id="14440-106">For example, you can configure calls to unassigned numbers to play a message, or to be transferred to a different destination, or both.</span></span>
  
<span data-ttu-id="14440-107">Приложение оповещения устанавливается как компонент приложения группы ответа на сервере переднего плана или сервере Standard Edition, при развертывании корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="14440-107">The Announcement application is installed as a feature of Response Group application on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="14440-108">Для настройки оповещений следует загрузить аудиофайлы или настроить преобразование текста в речь и сконфигурировать таблицу неприсвоенных номеров.</span><span class="sxs-lookup"><span data-stu-id="14440-108">You need to configure Announcements by uploading your audio files or by configuring text-to-speech (TTS) and configuring the unassigned number table.</span></span>
  
<span data-ttu-id="14440-109">В этом разделе Обзор действий, необходимых для развертывания приложения объявлений.</span><span class="sxs-lookup"><span data-stu-id="14440-109">This section provides an overview of the steps involved in deploying the Announcement application.</span></span> <span data-ttu-id="14440-110">Перед настройкой извещения, необходимо развернуть корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="14440-110">You must deploy Enterprise Voice before you configure announcements.</span></span> <span data-ttu-id="14440-111">Компоненты, необходимые для объявлений приложения установлены и включены при развертывании корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="14440-111">The components required by the Announcement application are installed and enabled when you deploy Enterprise Voice.</span></span>
  
<span data-ttu-id="14440-112">**Процесс развертывания объявлений**</span><span class="sxs-lookup"><span data-stu-id="14440-112">**Announcement Deployment Process**</span></span>

|<span data-ttu-id="14440-113">**Этап**</span><span class="sxs-lookup"><span data-stu-id="14440-113">**Phase**</span></span>|<span data-ttu-id="14440-114">**Действия**</span><span class="sxs-lookup"><span data-stu-id="14440-114">**Steps**</span></span>|<span data-ttu-id="14440-115">**Роли**</span><span class="sxs-lookup"><span data-stu-id="14440-115">**Roles**</span></span>|<span data-ttu-id="14440-116">**Документация по развертыванию**</span><span class="sxs-lookup"><span data-stu-id="14440-116">**Deployment documentation**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="14440-117">Настройка параметров объявлений</span><span class="sxs-lookup"><span data-stu-id="14440-117">Configure Announcement settings</span></span>  <br/> | <span data-ttu-id="14440-118">Создайте объявление, записав и отправив звуковые файлы или воспользовавшись преобразованием текста в речь.</span><span class="sxs-lookup"><span data-stu-id="14440-118">Create the announcement by recording and uploading audio files or by using text-to-speech (TTS).</span></span> <br/>  <span data-ttu-id="14440-119">Настройте диапазоны неназначенных номеров в таблице неназначенных номеров и свяжите их с соответствующим объявлением.</span><span class="sxs-lookup"><span data-stu-id="14440-119">Configure the unassigned number ranges in the unassigned number table and associate them with the appropriate announcement.</span></span> <br/> |<span data-ttu-id="14440-120">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="14440-120">RTCUniversalServerAdmins</span></span>  <br/> <span data-ttu-id="14440-121">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="14440-121">CsVoiceAdministrator</span></span>  <br/> <span data-ttu-id="14440-122">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="14440-122">CsServerAdministrator</span></span>  <br/> <span data-ttu-id="14440-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="14440-123">CsAdministrator</span></span>  <br/> <span data-ttu-id="14440-124">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="14440-124">CsViewOnlyAdministrator</span></span>  <br/> |[<span data-ttu-id="14440-125">Создание и удаление оповещения в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="14440-125">Create or delete an announcement in Skype for Business Server 2015</span></span>](create-an-announcement.md) <br/> [<span data-ttu-id="14440-126">Создание или изменение диапазона неназначенных номеров в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="14440-126">Create or modify an unassigned number range in Skype for Business Server 2015</span></span>](create-or-modify-an-unassigned-number-range.md) <br/> |
|<span data-ttu-id="14440-127">Проверка развертывания объявления</span><span class="sxs-lookup"><span data-stu-id="14440-127">Verify your Announcement deployment</span></span>  <br/> |<span data-ttu-id="14440-128">Выполните тестовое прослушивание объявлений, чтобы убедиться в их правильной работе.</span><span class="sxs-lookup"><span data-stu-id="14440-128">Test by listening to announcements to verify that your configuration works as expected.</span></span>  <br/> |-  <br/> |[<span data-ttu-id="14440-129">(Необязательно) Проверка развертывания объявлений в Скайп для бизнеса 2015</span><span class="sxs-lookup"><span data-stu-id="14440-129">(Optional) Verify Announcement deployment in Skype for Business 2015</span></span>](optional-verify-announcement-deployment.md) <br/> |
   

