---
title: Propriedades do servidor (página Segurança) – Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.serverproperties.security.f1
ms.assetid: f49aedc6-f145-4df1-8f69-d5d910f492c6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f709d42bf593b4933d9fc1fdc423c195967df382
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575015"
---
# <a name="server-properties-security-page---reporting-services"></a><span data-ttu-id="768eb-102">Propriedades do Servidor (página Segurança) - Reporting Services</span><span class="sxs-lookup"><span data-stu-id="768eb-102">Server Properties (Security Page) - Reporting Services</span></span>
  <span data-ttu-id="768eb-103">Use esta página para desativar recursos que podem comprometer um servidor de relatório potencialmente.</span><span class="sxs-lookup"><span data-stu-id="768eb-103">Use this page to turn off features that can potentially compromise a report server.</span></span> <span data-ttu-id="768eb-104">A desativação desse recurso limitará algumas funcionalidades, mas pode aprimorar a segurança geral do servidor de relatório, reduzindo ameaças específicas.</span><span class="sxs-lookup"><span data-stu-id="768eb-104">Turning off these features will limit some functionality, but can improve the overall security of the report server by mitigating specific threats.</span></span>  
  
 <span data-ttu-id="768eb-105">Para abrir essa página, inicie o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], conecte-se a uma instância de servidor de relatórios, clique com o botão direito do mouse no nome do servidor de relatórios e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="768eb-105">To open this page, start [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to a report server instance, right-click the report server name, and select **Properties**.</span></span> <span data-ttu-id="768eb-106">Clique em **Segurança** para abrir essa página.</span><span class="sxs-lookup"><span data-stu-id="768eb-106">Click **Security** to open this page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="768eb-107">Opções</span><span class="sxs-lookup"><span data-stu-id="768eb-107">Options</span></span>  
 <span data-ttu-id="768eb-108">**Habilitar a segurança integrada do Windows para as fontes de dados do relatório**</span><span class="sxs-lookup"><span data-stu-id="768eb-108">**Enable Windows integrated security for report data sources**</span></span>  
 <span data-ttu-id="768eb-109">Especifique se uma conexão com uma fonte de dados de relatório pode ser feita usando o token de segurança do Windows do usuário que solicitou o relatório.</span><span class="sxs-lookup"><span data-stu-id="768eb-109">Specify whether a connection to a report data source can be made using the Windows security token of the user who requested the report.</span></span>  
  
 <span data-ttu-id="768eb-110">Se esse recurso for desativado, o recurso de Segurança Integrada do Windows nas páginas de propriedades das fontes de dados do relatório se tornará indisponível.</span><span class="sxs-lookup"><span data-stu-id="768eb-110">If you turn off this feature, the Windows Integrated Security feature in the report data source property pages will be unavailable.</span></span> <span data-ttu-id="768eb-111">Se as fontes de dados do relatório estiverem configuradas para segurança integrada do Windows e você subsequentemente desativar esse recurso, o servidor de relatório atualizará imediatamente todas as propriedades de conexão da fonte de dados para solicitar credenciais.</span><span class="sxs-lookup"><span data-stu-id="768eb-111">If report data sources are configured for Windows integrated security and you subsequently turn off this feature, the report server will immediately update all data source connection properties to prompt for credentials.</span></span>  
  
 <span data-ttu-id="768eb-112">**Habilitar Relatórios Ad Hoc**</span><span class="sxs-lookup"><span data-stu-id="768eb-112">**Enable Ad Hoc Reporting**</span></span>  
 <span data-ttu-id="768eb-113">Especifique se os usuários podem executar consultas ad hoc de um relatório do Construtor de Relatórios, onde novos relatórios são automaticamente gerados quando um usuário clica nos dados de interesse.</span><span class="sxs-lookup"><span data-stu-id="768eb-113">Specify whether users can perform ad hoc queries from a Report Builder report, where new reports are automatically generated when a user clicks data of interest.</span></span>  
  
 <span data-ttu-id="768eb-114">A definição dessa opção determina se a propriedade `EnableLoadReportDefinition` no servidor de relatório é definida como `True` ou `False`.</span><span class="sxs-lookup"><span data-stu-id="768eb-114">Setting this option determines whether the `EnableLoadReportDefinition` property on the report server is set to `True` or `False`.</span></span> <span data-ttu-id="768eb-115">Se você desmarcar esta opção, a propriedade será definida como `False` e o servidor de relatório não gerará relatórios de clickthrough criados durante a exploração dos dados.</span><span class="sxs-lookup"><span data-stu-id="768eb-115">If you clear this option, the property will be set to `False` and report server will not generate clickthrough reports that are created during data exploration.</span></span> <span data-ttu-id="768eb-116">Todas as chamadas para o método `LoadReportDefinition` serão bloqueadas.</span><span class="sxs-lookup"><span data-stu-id="768eb-116">All calls to the `LoadReportDefinition` method will be blocked.</span></span>  
  
 <span data-ttu-id="768eb-117">A desativação dessa opção reduz uma ameaça de que um usuário mal-intencionado inicie um ataque de negação de serviço, sobrecarregando o servidor de relatório com solicitações `LoadReportDefinition`.</span><span class="sxs-lookup"><span data-stu-id="768eb-117">Turning off this option mitigates a threat whereby a malicious user launches a denial of service attack by overloading the report server with `LoadReportDefinition` requests.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="768eb-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="768eb-118">See Also</span></span>  
 <span data-ttu-id="768eb-119">[Definir propriedades do servidor de relatório &#40;Management Studio&#41;](set-report-server-properties-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="768eb-119">[Set Report Server Properties &#40;Management Studio&#41;](set-report-server-properties-management-studio.md) </span></span>  
 <span data-ttu-id="768eb-120">[Conectar-se a um servidor de relatório no Management Studio](connect-to-a-report-server-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="768eb-120">[Connect to a Report Server in Management Studio](connect-to-a-report-server-in-management-studio.md) </span></span>  
 <span data-ttu-id="768eb-121">[Especificar informações de credencial e de conexão para fontes de dados de relatório] (.. /Report-data/Specify-Credential-and-Connection-Information-for-Report-Data-Sources.MD o [servidor de relatório na ajuda F1 do Management Studio](report-server-in-management-studio-f1-help.md)</span><span class="sxs-lookup"><span data-stu-id="768eb-121">[Specify Credential and Connection Information for Report Data Sources](../report-data/specify-credential-and-connection-information-for-report-data-sources.md [Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md)</span></span>  
  
  
