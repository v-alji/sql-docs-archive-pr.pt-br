---
title: Implantar soluções de modelo usando XMLA | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- XML scripts [Analysis Services]
- scripts [Analysis Services], deployment
- deploying [Analysis Services], XML scripts
- Analysis Services deployments, XML scripts
ms.assetid: a8cb1837-fcac-4730-bea4-a72cf94d9f7c
author: minewiskan
ms.author: owend
ms.openlocfilehash: b78490c5ab6ad3ba5e52bb82d4be254e3f5f102b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685348"
---
# <a name="deploy-model-solutions-using-xmla"></a><span data-ttu-id="3baca-102">Implantar soluções de modelo usando XMLA</span><span class="sxs-lookup"><span data-stu-id="3baca-102">Deploy Model Solutions Using XMLA</span></span>
  <span data-ttu-id="3baca-103">No [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], a opção **CREATE To** do comando **Script de Banco de Dados como** cria um script XML de um banco de dados inteiro do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ou de um de seus objetos constituintes.</span><span class="sxs-lookup"><span data-stu-id="3baca-103">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], the **CREATE To** option of the **Script Database As** command creates an XML script of an entire [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database or one of its constituent objects.</span></span> <span data-ttu-id="3baca-104">O script resultante pode ser executado em outro computador para recriar o esquema (metadados) do banco de dados do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3baca-104">The resulting script can then be run on another computer to recreate the schema (metadata) of the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span> <span data-ttu-id="3baca-105">O script gera o banco de dados inteiro e não há nenhum mecanismo para atualizar de maneira incremental objetos já implantados ao usar o script.</span><span class="sxs-lookup"><span data-stu-id="3baca-105">The script generates the entire database, and there is no mechanism for incrementally updating already deployed objects when using the script.</span></span> <span data-ttu-id="3baca-106">Depois de executar o script e implantar o banco de dados, o banco de dados recém-criado deve ser processado antes de os usuários poderem navegar nele.</span><span class="sxs-lookup"><span data-stu-id="3baca-106">After running the script and deploying the database, the newly created database must be processed before users can browse it.</span></span>  
  
 <span data-ttu-id="3baca-107">Para obter mais informações sobre o comando **Script de Banco de Dados como** , consulte [Documentar e gerar scripts de um banco de dados do Analysis Services](document-and-script-an-analysis-services-database.md).</span><span class="sxs-lookup"><span data-stu-id="3baca-107">For more information about the **Script Database As** command, see [Document and Script an Analysis Services Database](document-and-script-an-analysis-services-database.md).</span></span>  
  
## <a name="modifying-object-properties-in-the-xml-script"></a><span data-ttu-id="3baca-108">Modificando as propriedades do objeto no script XML</span><span class="sxs-lookup"><span data-stu-id="3baca-108">Modifying Object Properties in the XML Script</span></span>  
 <span data-ttu-id="3baca-109">Ao usar o comando **Script de Banco de Dados como** , você não pode modificar propriedades específicas (como o nome do banco de dados, as cadeias de caracteres de conexão da fonte de dados e as configurações de segurança) dos objetos do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="3baca-109">When using the **Script Database As** command, you cannot modify specific properties (such as the database name, data source connection strings, and security settings) of the database objects.</span></span> <span data-ttu-id="3baca-110">Essas propriedades devem ser modificadas manualmente no script depois que o script tiver sido gerado ou devem ser modificadas no banco de dados implantado depois de executar o script.</span><span class="sxs-lookup"><span data-stu-id="3baca-110">These properties must either be manually modified in the script after the script has been generated or modified in the deployed database after running the script.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="3baca-111">O script XML não conterá a senha se isso for especificado na cadeia de caracteres de conexão para uma fonte de dados ou para propósitos de representação.</span><span class="sxs-lookup"><span data-stu-id="3baca-111">The XML script will not contain the password if this is specified in either the connection string for a data source or for impersonation purposes.</span></span> <span data-ttu-id="3baca-112">Considerando que a senha é necessária para propósitos de processamento nesse cenário, você precisará adicioná-la manualmente ao script XML antes de ele ser executado ou adicioná-la depois que o script XML tiver sido executado.</span><span class="sxs-lookup"><span data-stu-id="3baca-112">Since the password is required for processing purposes in this scenario, you will either need to add this manually to the XML script before it executes or add it after the XML script executes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3baca-113">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3baca-113">See Also</span></span>  
 <span data-ttu-id="3baca-114">[Implantar soluções de modelo usando o assistente de implantação](deploy-model-solutions-using-the-deployment-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="3baca-114">[Deploy Model Solutions Using the Deployment Wizard](deploy-model-solutions-using-the-deployment-wizard.md) </span></span>  
 [<span data-ttu-id="3baca-115">Sincronizar bancos de dados do Analysis Services</span><span class="sxs-lookup"><span data-stu-id="3baca-115">Synchronize Analysis Services Databases</span></span>](synchronize-analysis-services-databases.md)  
  
  
