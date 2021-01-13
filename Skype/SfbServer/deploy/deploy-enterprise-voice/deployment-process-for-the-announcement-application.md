---
title: Процесс развертывания приложения объявлений в Skype для бизнеса Server
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
ms.assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
description: Процесс развертывания приложения объявлений в Skype для бизнеса Server Корпоративная голосовая связь.
ms.openlocfilehash: cfb1436f22681b45de5c399907d4776a9d1db5de
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812309"
---
# <a name="deployment-process-for-the-announcement-application-in-skype-for-business-server"></a><span data-ttu-id="598a8-103">Процесс развертывания приложения объявлений в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="598a8-103">Deployment process for the Announcement application in Skype for Business Server</span></span>
 
<span data-ttu-id="598a8-104">Процесс развертывания приложения объявлений в Skype для бизнеса Server Корпоративная голосовая связь.</span><span class="sxs-lookup"><span data-stu-id="598a8-104">Deployment process and steps for Announcement application in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="598a8-105">Приложение "Объявление" — это функция Корпоративная голосовая связь, которая позволяет настроить, что происходит с вызовами ненаписаных расширений (расширения, допустимые для вашей организации, но не назначены человеку или телефону).</span><span class="sxs-lookup"><span data-stu-id="598a8-105">The Announcement application is an Enterprise Voice feature that enables you to configure what happens to calls to unassigned extensions (extensions that are valid for your organization, but are not assigned to a person or a phone).</span></span> <span data-ttu-id="598a8-106">Например, можно настроить эту функцию таким образом, чтобы при выполнении вызовов на неприсвоенные номера воспроизводилось сообщение и/или эти вызовы передавались на другое назначение.</span><span class="sxs-lookup"><span data-stu-id="598a8-106">For example, you can configure calls to unassigned numbers to play a message, or to be transferred to a different destination, or both.</span></span>
  
<span data-ttu-id="598a8-107">Приложение "Объявление" устанавливается как функция приложения группы ответа на сервере переднего Корпоративная голосовая связь.</span><span class="sxs-lookup"><span data-stu-id="598a8-107">The Announcement application is installed as a feature of Response Group application on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="598a8-108">Для настройки оповещений следует загрузить аудиофайлы или настроить преобразование текста в речь и сконфигурировать таблицу неприсвоенных номеров.</span><span class="sxs-lookup"><span data-stu-id="598a8-108">You need to configure Announcements by uploading your audio files or by configuring text-to-speech (TTS) and configuring the unassigned number table.</span></span>
  
<span data-ttu-id="598a8-109">В этом разделе представлен обзор действий, необходимых для развертывания приложения "Объявление".</span><span class="sxs-lookup"><span data-stu-id="598a8-109">This section provides an overview of the steps involved in deploying the Announcement application.</span></span> <span data-ttu-id="598a8-110">Необходимо развернуть Корпоративная голосовая связь перед настройкой объявлений.</span><span class="sxs-lookup"><span data-stu-id="598a8-110">You must deploy Enterprise Voice before you configure announcements.</span></span> <span data-ttu-id="598a8-111">Компоненты, необходимые приложению "Объявление", устанавливаются и включаются при развертывании Корпоративная голосовая связь.</span><span class="sxs-lookup"><span data-stu-id="598a8-111">The components required by the Announcement application are installed and enabled when you deploy Enterprise Voice.</span></span>
  
<span data-ttu-id="598a8-112">**Процесс развертывания объявлений**</span><span class="sxs-lookup"><span data-stu-id="598a8-112">**Announcement Deployment Process**</span></span>

|<span data-ttu-id="598a8-113">**Этап**</span><span class="sxs-lookup"><span data-stu-id="598a8-113">**Phase**</span></span>|<span data-ttu-id="598a8-114">**Действия**</span><span class="sxs-lookup"><span data-stu-id="598a8-114">**Steps**</span></span>|<span data-ttu-id="598a8-115">**Roles**</span><span class="sxs-lookup"><span data-stu-id="598a8-115">**Roles**</span></span>|<span data-ttu-id="598a8-116">**Документация по развертыванию**</span><span class="sxs-lookup"><span data-stu-id="598a8-116">**Deployment documentation**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="598a8-117">Настройка параметров объявлений</span><span class="sxs-lookup"><span data-stu-id="598a8-117">Configure Announcement settings</span></span>  <br/> | <span data-ttu-id="598a8-118">Создайте объявление, записав и отправив звуковые файлы или воспользовавшись преобразованием текста в речь.</span><span class="sxs-lookup"><span data-stu-id="598a8-118">Create the announcement by recording and uploading audio files or by using text-to-speech (TTS).</span></span> <br/>  <span data-ttu-id="598a8-119">Настройте диапазоны неназначенных номеров в таблице неназначенных номеров и свяжите их с соответствующим объявлением.</span><span class="sxs-lookup"><span data-stu-id="598a8-119">Configure the unassigned number ranges in the unassigned number table and associate them with the appropriate announcement.</span></span> <br/> |<span data-ttu-id="598a8-120">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="598a8-120">RTCUniversalServerAdmins</span></span>  <br/> <span data-ttu-id="598a8-121">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="598a8-121">CsVoiceAdministrator</span></span>  <br/> <span data-ttu-id="598a8-122">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="598a8-122">CsServerAdministrator</span></span>  <br/> <span data-ttu-id="598a8-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="598a8-123">CsAdministrator</span></span>  <br/> <span data-ttu-id="598a8-124">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="598a8-124">CsViewOnlyAdministrator</span></span>  <br/> |[<span data-ttu-id="598a8-125">Создание или удаление объявления в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="598a8-125">Create or delete an announcement in Skype for Business Server</span></span>](create-an-announcement.md) <br/> [<span data-ttu-id="598a8-126">Создание или изменение диапазона ненаписаных номеров в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="598a8-126">Create or modify an unassigned number range in Skype for Business Server</span></span>](create-or-modify-an-unassigned-number-range.md) <br/> |
|<span data-ttu-id="598a8-127">Проверка развертывания объявления</span><span class="sxs-lookup"><span data-stu-id="598a8-127">Verify your Announcement deployment</span></span>  <br/> |<span data-ttu-id="598a8-128">Выполните тестовое прослушивание объявлений, чтобы убедиться в их правильной работе.</span><span class="sxs-lookup"><span data-stu-id="598a8-128">Test by listening to announcements to verify that your configuration works as expected.</span></span>  <br/> |-  <br/> |[<span data-ttu-id="598a8-129">(Необязательно) Проверка развертывания объявлений в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="598a8-129">(Optional) Verify Announcement deployment in Skype for Business</span></span>](optional-verify-announcement-deployment.md) <br/> |
   

