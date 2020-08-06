---
title: Extensões personalizadas foram detectadas no servidor de relatório (Supervisor de atualização) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- rendering extensions [Reporting Services], custom extensions
- security extensions [Reporting Services]
- custom extensions [Reporting Services]
- data processing extensions [Reporting Services], custom extensions
- delivery extensions [Reporting Services]
ms.assetid: fa184bd7-11d6-4ea3-9249-bc1b13db49e5
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: e4be596ff0f110515155f2aa14dc00aceaf85efd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571774"
---
# <a name="custom-extensions-were-detected-on-the-report-server-upgrade-advisor"></a><span data-ttu-id="12ea6-102">Extensões personalizadas foram detectadas no servidor de relatório (Supervisor de Atualização)</span><span class="sxs-lookup"><span data-stu-id="12ea6-102">Custom extensions were detected on the report server (Upgrade Advisor)</span></span>
  <span data-ttu-id="12ea6-103">O Supervisor de Atualização detectou configurações de extensão personalizada nos arquivos de configuração, o que indica que sua instalação tem uma ou mais extensões personalizadas para processamento de dados, entrega, renderização, segurança ou autenticação.</span><span class="sxs-lookup"><span data-stu-id="12ea6-103">Upgrade Advisor detected custom extension settings in the configuration files, indicating that your installation includes one or more custom extensions for data processing, delivery, rendering, security, or authentication.</span></span> <span data-ttu-id="12ea6-104">A atualização moverá os parâmetros de configuração de extensão com o servidor de relatório atualizado.</span><span class="sxs-lookup"><span data-stu-id="12ea6-104">Upgrade will move the extension configuration settings with the upgraded report server.</span></span> <span data-ttu-id="12ea6-105">No entanto, se houver extensões personalizadas instaladas na pasta existente do servidor de relatório, os arquivos de assembly dessas extensões personalizadas não serão movidos para a nova pasta de instalação durante o processo de atualização.</span><span class="sxs-lookup"><span data-stu-id="12ea6-105">However, if the custom extensions are installed in the existing report server installation folder, the assembly files for those custom extensions will not be moved to the new installation folder during the upgrade process.</span></span> <span data-ttu-id="12ea6-106">Concluída a atualização, mova os arquivos de assembly para a nova pasta de instalação do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="12ea6-106">After upgrade completes, you must move the assembly files to the new [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation folder.</span></span>  
  
||  
|-|  
|<span data-ttu-id="12ea6-107">**[!INCLUDE[applies](../../includes/applies-md.md)]** Modo nativo do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] &#124; [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] modo do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="12ea6-107">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode &#124; [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="12ea6-108">Componente</span><span class="sxs-lookup"><span data-stu-id="12ea6-108">Component</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a><span data-ttu-id="12ea6-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="12ea6-109">Description</span></span>  
 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]<span data-ttu-id="12ea6-110">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]fornece uma arquitetura extensível que permite aos desenvolvedores criar extensões personalizadas para processamento de dados, entrega, renderização, segurança e autenticação.</span><span class="sxs-lookup"><span data-stu-id="12ea6-110">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] provides an extensible architecture that allows developers to create custom extensions for data processing, delivery, rendering, security, and authentication.</span></span>  
  
 <span data-ttu-id="12ea6-111">Se forem usados extensões ou assemblies personalizados na instalação do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], será possível usar a Instalação para fazer uma atualização, mas talvez seja necessário mover as extensões para o novo local de instalação ao final da atualização ou executar as etapas anteriores à atualização.</span><span class="sxs-lookup"><span data-stu-id="12ea6-111">If custom extensions or assemblies are used in your [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation, you can use Setup to perform an upgrade, but you may need to move extensions to the new installation location after upgrade completes, or you may need to perform steps prior to upgrade.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="12ea6-112">O Supervisor de Atualização não detecta se os assemblies de código personalizados foram configurados para uso em relatórios para calcular valores de item, estilos e formatação.</span><span class="sxs-lookup"><span data-stu-id="12ea6-112">Upgrade Advisor does not detect whether custom code assemblies are configured for use in reports to calculate item values, styles, and formatting.</span></span> <span data-ttu-id="12ea6-113">Para obter mais informações, consulte [outros Reporting Services problemas de atualização](../../../2014/sql-server/install/other-reporting-services-upgrade-issues.md).</span><span class="sxs-lookup"><span data-stu-id="12ea6-113">For more information, see [Other Reporting Services Upgrade Issues](../../../2014/sql-server/install/other-reporting-services-upgrade-issues.md).</span></span>  
  
 <span data-ttu-id="12ea6-114">Se você adquiriu as extensões personalizadas de um fornecedor de software, entre em contato com ele para obter mais informações sobre a atualização da sua funcionalidade personalizada.</span><span class="sxs-lookup"><span data-stu-id="12ea6-114">If you purchased custom extensions from a software vendor, check with the vendor for additional information about upgrading your custom functionality.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="12ea6-115">Ação corretiva</span><span class="sxs-lookup"><span data-stu-id="12ea6-115">Corrective Action</span></span>  
 <span data-ttu-id="12ea6-116">Use as seções seguintes para determinar as etapas que devem ser executadas depois ou antes de executar uma atualização do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="12ea6-116">Use the following sections to determine steps to perform in addition to or prior to performing an upgrade of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]:</span></span>  
  
 [<span data-ttu-id="12ea6-117">Extensões de processamento de dados ou de entrega personalizadas</span><span class="sxs-lookup"><span data-stu-id="12ea6-117">Custom data processing or delivery extensions</span></span>](#dataprocdeliver)  
  
 [<span data-ttu-id="12ea6-118">Extensões de renderização personalizadas</span><span class="sxs-lookup"><span data-stu-id="12ea6-118">Custom rendering extensions</span></span>](#render)  
  
 [<span data-ttu-id="12ea6-119">Extensões de segurança ou de autenticação personalizadas em um servidor de relatório do SQL Server 2000</span><span class="sxs-lookup"><span data-stu-id="12ea6-119">Custom security or authentication extensions on a SQL Server 2000 report server</span></span>](#secauth2000)  
  
 [<span data-ttu-id="12ea6-120">Extensões de segurança de autenticação personalizadas em um servidor de relatório do SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="12ea6-120">Custom security or authentication extensions on a SQL Server 2005 report server</span></span>](#secauth2005)  
  
 <span data-ttu-id="12ea6-121">Concluída a atualização, mova os assemblies de extensão para a nova pasta de instalação e, em seguida, verifique se as extensões personalizadas funcionam como previsto.</span><span class="sxs-lookup"><span data-stu-id="12ea6-121">After upgrade completes, move the extension assemblies to the new installation folder and then verify that the custom extensions work as expected.</span></span> <span data-ttu-id="12ea6-122">Se a extensão não funcionar, será necessária uma nova recompilação.</span><span class="sxs-lookup"><span data-stu-id="12ea6-122">If your extension does not work, you might have to recompile it.</span></span>  
  
#### <a name="to-recompile-an-extension"></a><span data-ttu-id="12ea6-123">Para recompilar uma extensão</span><span class="sxs-lookup"><span data-stu-id="12ea6-123">To recompile an extension</span></span>  
  
1.  <span data-ttu-id="12ea6-124">Copie o arquivo Microsoft.ReportingServices.Interfaces.dll para a pasta que contém seu código-fonte.</span><span class="sxs-lookup"><span data-stu-id="12ea6-124">Copy the Microsoft.ReportingServices.Interfaces.dll file to the folder that contains your source code.</span></span>  
  
2.  <span data-ttu-id="12ea6-125">Abra o projeto que contém seus arquivos de origem e adicione uma referência ao arquivo Microsoft.ReportingServices.Interfaces.dll.</span><span class="sxs-lookup"><span data-stu-id="12ea6-125">Open the project that contains your source files and add a reference to the Microsoft.ReportingServices.Interfaces.dll file.</span></span>  
  
3.  <span data-ttu-id="12ea6-126">Recrie a solução para associá-la à extensão.</span><span class="sxs-lookup"><span data-stu-id="12ea6-126">Rebuild the solution to bind the extension.</span></span>  
  
 <span data-ttu-id="12ea6-127">Se você decidir não continuar com a atualização, convém migrar o [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="12ea6-127">If you decide not to continue with upgrade, you might decide to migrate [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instead.</span></span> <span data-ttu-id="12ea6-128">Para obter as etapas de migração de extensões personalizadas, consulte [migrando extensões personalizadas](#migrcustext) neste tópico.</span><span class="sxs-lookup"><span data-stu-id="12ea6-128">For steps on migrating custom extensions, see [Migrating custom extensions](#migrcustext) in this topic.</span></span>  
  
###  <a name="custom-data-processing-or-delivery-extensions"></a><a name="dataprocdeliver"></a><span data-ttu-id="12ea6-129">Processamento de dados personalizado ou extensões de entrega</span><span class="sxs-lookup"><span data-stu-id="12ea6-129">Custom data processing or delivery extensions</span></span>  
 <span data-ttu-id="12ea6-130">Se o Supervisor de Atualização detectar extensões de processamento de dados ou de entrega personalizadas, o processo de atualização não será bloqueado.</span><span class="sxs-lookup"><span data-stu-id="12ea6-130">If Upgrade Advisor detects custom data processing or delivery extensions, the upgrade process is not blocked.</span></span> <span data-ttu-id="12ea6-131">No entanto, concluída a atualização, pode ser necessário executar etapas adicionais para que a funcionalidade personalizada fornecida por essas extensões funcione.</span><span class="sxs-lookup"><span data-stu-id="12ea6-131">However, after upgrade completes, you might need to perform additional steps before the custom functionality provided by these extensions will work.</span></span> <span data-ttu-id="12ea6-132">Por exemplo, você terá que executar etapas adicionais quando os arquivos de extensão personalizados forem instalados na pasta de instalação do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="12ea6-132">For example, you must perform additional steps when the custom extension files are installed in the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation folder.</span></span>  
  
##### <a name="post-upgrade-steps-for-custom-data-processing-or-delivery-extensions"></a><span data-ttu-id="12ea6-133">Etapas pós-atualização para extensões de processamento de dados ou de entrega personalizadas</span><span class="sxs-lookup"><span data-stu-id="12ea6-133">Post-upgrade steps for custom data processing or delivery extensions</span></span>  
  
1.  <span data-ttu-id="12ea6-134">Mova os arquivos de extensão para a nova pasta de programa do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="12ea6-134">Move the extension file or files to the new program folder for the report server.</span></span> <span data-ttu-id="12ea6-135">Por padrão, a pasta de programa do servidor de relatório está em \Program Files\Microsoft SQL Server \ MSRS10_50. \<*instance_name*> servidor \report.</span><span class="sxs-lookup"><span data-stu-id="12ea6-135">By default, the report server program folder is in \Program Files\Microsoft SQL Server\MSRS10_50.\<*instance_name*>\report server.</span></span>  
  
 <span data-ttu-id="12ea6-136">Para obter mais informações, consulte "Implantando uma extensão de processamento de dados" e "Implementando uma extensão de entrega" nos Manuais Online do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="12ea6-136">For more information, see "Deploying a Data Processing Extension" and "Implementing a Delivery Extension" in SQL Server Books Online.</span></span>  
  
###  <a name="custom-rendering-extensions"></a><a name="render"></a><span data-ttu-id="12ea6-137">Extensões de renderização personalizadas</span><span class="sxs-lookup"><span data-stu-id="12ea6-137">Custom rendering extensions</span></span>  
 <span data-ttu-id="12ea6-138">Se o Supervisor de Atualização detectar extensões de renderização personalizadas, o processo de atualização será bloqueado.</span><span class="sxs-lookup"><span data-stu-id="12ea6-138">If Upgrade Advisor detects custom rendering extensions, the upgrade process is blocked.</span></span> <span data-ttu-id="12ea6-139">Você pode prosseguir com o processo de atualização removendo as entradas de configuração das extensões personalizadas do arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="12ea6-139">You can continue with the upgrade process by removing the custom extension configuration entries from the configuration file.</span></span> <span data-ttu-id="12ea6-140">No entanto, isso tornará as extensões personalizadas indisponíveis para os usuários depois da atualização.</span><span class="sxs-lookup"><span data-stu-id="12ea6-140">However, this will cause the custom extensions to be unavailable to users after upgrade completes.</span></span> <span data-ttu-id="12ea6-141">Se você precisar de extensões de renderização personalizadas depois da atualização, terá que criar extensões de renderização atualizadas ou obtê-las com um fornecedor de extensão personalizada.</span><span class="sxs-lookup"><span data-stu-id="12ea6-141">If you need custom rendering extensions after upgrade, you must build updated rendering extensions or obtain updated rendering extensions from a custom extension vendor.</span></span>  
  
 <span data-ttu-id="12ea6-142">Você deve executar etapas para habilitar uma atualização ou pode escolher migrar o [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="12ea6-142">You must perform steps to enable an upgrade or you may chose to migrate [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instead.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="12ea6-143">Não atualize ou migre o servidor de relatório antes de testar e verificar se a extensão de renderização atualizada funciona como esperado.</span><span class="sxs-lookup"><span data-stu-id="12ea6-143">Do not upgrade or migrate your report server until you have tested and verified that the updated rendering extension works as expected.</span></span>  
  
##### <a name="to-upgrade-custom-rendering-extensions"></a><span data-ttu-id="12ea6-144">Para atualizar extensões de renderização personalizadas</span><span class="sxs-lookup"><span data-stu-id="12ea6-144">To upgrade custom rendering extensions</span></span>  
  
1.  <span data-ttu-id="12ea6-145">Obtenha extensões de renderização com as interfaces mais recentes.</span><span class="sxs-lookup"><span data-stu-id="12ea6-145">Obtain rendering extensions with the latest interfaces.</span></span>  
  
2.  <span data-ttu-id="12ea6-146">Remova a entrada de extensão de renderização personalizada antiga ou as entradas de RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="12ea6-146">Remove the old custom rendering extension entry or entries from RSReportServer.config.</span></span>  
  
3.  <span data-ttu-id="12ea6-147">Atualize o servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="12ea6-147">Upgrade the report server.</span></span>  
  
4.  <span data-ttu-id="12ea6-148">Concluída a atualização, instale as extensões atualizadas no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="12ea6-148">After upgrade completes, install the updated extensions on the report server.</span></span>  
  
 <span data-ttu-id="12ea6-149">Para obter mais informações, consulte “Implementando uma extensão de renderização" nos Manuais Online do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="12ea6-149">For more information, see "Implementing a Rendering Extension" in SQL Server Books Online.</span></span>  
  
###  <a name="custom-security-or-authentication-extensions-on-a-sql-server-2000-report-server"></a><a name="secauth2000"></a><span data-ttu-id="12ea6-150">Extensões de segurança ou de autenticação personalizadas em um servidor de relatório SQL Server 2000</span><span class="sxs-lookup"><span data-stu-id="12ea6-150">Custom security or authentication extensions on a SQL Server 2000 report server</span></span>  
 <span data-ttu-id="12ea6-151">Se o Supervisor de Atualização detectar extensões de segurança ou de autenticação personalizadas em um servidor de relatório do [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], o processo de atualização será bloqueado.</span><span class="sxs-lookup"><span data-stu-id="12ea6-151">If Upgrade Advisor detects custom security or authentication extensions on a [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] report server, the upgrade process is blocked.</span></span> <span data-ttu-id="12ea6-152">Você deve executar etapas para habilitar uma atualização ou pode escolher migrar o [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="12ea6-152">You must perform steps to enable an upgrade or you may chose to migrate [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instead.</span></span> <span data-ttu-id="12ea6-153">Em qualquer das hipóteses, atualize e recompile as extensões com as interfaces mais recentes em Microsoft.ReportingServices.Interfaces.dll, pois as interfaces mudaram entre o [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] e o [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="12ea6-153">In either case, you must update and recompile the extensions with the latest interfaces in Microsoft.ReportingServices.Interfaces.dll, because the interfaces have changed between [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] and [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="12ea6-154">Não atualize ou migre o servidor de relatório antes de testar e verificar se a extensão de segurança ou de autenticação atualizada funciona como esperado.</span><span class="sxs-lookup"><span data-stu-id="12ea6-154">Do not upgrade or migrate your report server until you have tested and verified that the updated security or authentication extension works as expected.</span></span>  
  
 <span data-ttu-id="12ea6-155">Se você estiver usando uma extensão de autenticação personalizada criada para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2000 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], deverá modificar o código-fonte para que haja suporte para novas classes e membros apresentados nos relatórios controlados por modelos.</span><span class="sxs-lookup"><span data-stu-id="12ea6-155">If you are using a custom authentication extension that you created for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2000 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you must modify the source code to support new classes and members introduced for model-driven reporting.</span></span>  
  
##### <a name="to-upgrade-custom-security-or-authentication-extensions-from-a-sql-server-2000-report-server"></a><span data-ttu-id="12ea6-156">Para atualizar a segurança personalizada ou extensões de autenticação de um servidor de relatório SQL Server 2000</span><span class="sxs-lookup"><span data-stu-id="12ea6-156">To upgrade custom security or authentication extensions from a SQL Server 2000 report server</span></span>  
  
1.  <span data-ttu-id="12ea6-157">Atualize e recompile qualquer extensão de segurança ou de autenticação com as interfaces mais recentes.</span><span class="sxs-lookup"><span data-stu-id="12ea6-157">Update and recompile any security or authentication extensions with the latest interfaces.</span></span>  
  
2.  <span data-ttu-id="12ea6-158">Remova as entradas de extensão de segurança ou de autenticação de RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="12ea6-158">Remove the security or authentication extension entry or entries from RSReportServer.config.</span></span>  
  
3.  <span data-ttu-id="12ea6-159">Atualize o servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="12ea6-159">Upgrade the report server.</span></span>  
  
4.  <span data-ttu-id="12ea6-160">Concluída a atualização, instale as extensões atualizadas no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="12ea6-160">After upgrade completes, install the updated extensions on the report server.</span></span>  
  
 <span data-ttu-id="12ea6-161">Para obter mais informações, consulte “Implementando uma extensão de segurança" nos Manuais Online do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="12ea6-161">For more information, see "Implementing a Security Extension" in SQL Server Books Online.</span></span>  
  
###  <a name="custom-security-or-authentication-extensions-on-a-sql-server-2005-report-server"></a><a name="secauth2005"></a><span data-ttu-id="12ea6-162">Extensões de segurança ou de autenticação personalizadas em um servidor de relatório SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="12ea6-162">Custom security or authentication extensions on a SQL Server 2005 report server</span></span>  
 <span data-ttu-id="12ea6-163">Se o Supervisor de Atualização detectar extensões de segurança ou de autenticação personalizadas em um servidor de relatório do [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], o processo de atualização será bloqueado.</span><span class="sxs-lookup"><span data-stu-id="12ea6-163">If Upgrade Advisor detects custom security or authentication extensions on a [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] report server, the upgrade process is blocked.</span></span> <span data-ttu-id="12ea6-164">Você deve executar etapas para habilitar uma atualização ou pode escolher migrar o [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="12ea6-164">You must perform steps to enable an upgrade or you may chose to migrate [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instead.</span></span>  
  
##### <a name="to-upgrade-custom-security-or-authentication-extensions-from-a-sql-server-2005-report-server"></a><span data-ttu-id="12ea6-165">Para atualizar extensões de segurança ou de autenticação personalizadas de um servidor de relatório do SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="12ea6-165">To upgrade custom security or authentication extensions from a SQL Server 2005 report server</span></span>  
  
1.  <span data-ttu-id="12ea6-166">Remova as entradas da configuração da extensão de segurança ou de autenticação de RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="12ea6-166">Remove the security or authentication extension configuration entries from RSReportServer.config.</span></span>  
  
2.  <span data-ttu-id="12ea6-167">Atualize o servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="12ea6-167">Upgrade the report server.</span></span>  
  
3.  <span data-ttu-id="12ea6-168">Concluída a atualização, adicione as entradas de configuração novamente a RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="12ea6-168">After upgrade completes, add the configuration entries back in RSReportServer.config.</span></span>  
  
4.  <span data-ttu-id="12ea6-169">Se os assemblies de extensão foram instalados na pasta de instalação antiga do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], em seguida, mova-os para a nova pasta de instalação.</span><span class="sxs-lookup"><span data-stu-id="12ea6-169">If the extension assemblies were installed in the old [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation folder, move then to the new installation folder.</span></span>  
  
 <span data-ttu-id="12ea6-170">Para obter mais informações, consulte “Implementando uma extensão de segurança" nos Manuais Online do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="12ea6-170">For more information, see "Implementing a Security Extension" in SQL Server Books Online.</span></span>  
  
###  <a name="migrating-custom-extensions"></a><a name="migrcustext"></a><span data-ttu-id="12ea6-171">Migrando extensões personalizadas</span><span class="sxs-lookup"><span data-stu-id="12ea6-171">Migrating custom extensions</span></span>  
 <span data-ttu-id="12ea6-172">Se você decidir migrar o [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] em vez de executar uma atualização, use as etapas para migrar extensões personalizadas para a nova instância do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="12ea6-172">If you decide to migrate [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instead performing an upgrade, use the steps to migrate custom extensions to the new [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instance.</span></span>  
  
##### <a name="to-migrate-custom-extensions-to-a-new-reporting-services-instance"></a><span data-ttu-id="12ea6-173">Para migrar extensões personalizadas para uma nova instância do Reporting Services</span><span class="sxs-lookup"><span data-stu-id="12ea6-173">To migrate custom extensions to a new Reporting Services instance</span></span>  
  
1.  <span data-ttu-id="12ea6-174">Crie ou obtenha extensões atualizadas com as interfaces mais recentes do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="12ea6-174">Build or obtain updated extensions with the latest [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] interfaces.</span></span>  
  
2.  <span data-ttu-id="12ea6-175">Migre o servidor de relatório para uma nova instância.</span><span class="sxs-lookup"><span data-stu-id="12ea6-175">Migrate the report server to a new instance.</span></span>  
  
3.  <span data-ttu-id="12ea6-176">Configure as extensões na nova instância.</span><span class="sxs-lookup"><span data-stu-id="12ea6-176">Configure the extensions on the new instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12ea6-177">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="12ea6-177">See Also</span></span>  
 [<span data-ttu-id="12ea6-178">Problemas de atualização do Reporting Services &#40;o supervisor de atualização&#41;</span><span class="sxs-lookup"><span data-stu-id="12ea6-178">Reporting Services Upgrade Issues &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/reporting-services-upgrade-issues-upgrade-advisor.md)  
  
  
