---
title: Referência da interface do usuário da caixa de diálogo funções do pacote | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.dtsserver.packageroles.f1
helpviewer_keywords:
- Package Roles dialog box
ms.assetid: 63f13416-c0aa-4480-a336-ef1e6e31a860
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 389b29ddee5674af7ecd106f4f82d61bbb3a0f36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681789"
---
# <a name="package-roles-dialog-box-ui-reference"></a><span data-ttu-id="683a1-102">Referência da interface do usuário da caixa de diálogo Funções do Pacote</span><span class="sxs-lookup"><span data-stu-id="683a1-102">Package Roles Dialog Box UI Reference</span></span>
  <span data-ttu-id="683a1-103">Use a caixa de diálogo **Funções do Pacote** , disponível no [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], para especificar as funções de nível de banco de dados que têm acesso de leitura e as que têm acesso de gravação ao pacote.</span><span class="sxs-lookup"><span data-stu-id="683a1-103">Use the **Package Roles** dialog box, available in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], to specify the database-level roles that have read access to the package and the database-level roles that have write access to the package.</span></span> <span data-ttu-id="683a1-104">As funções de nível de banco de dados se aplicam apenas a pacotes armazenados no banco de dados [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] **msdb**.</span><span class="sxs-lookup"><span data-stu-id="683a1-104">Database-level roles apply only to packages that are stored in the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] **msdb** database.</span></span>  
  
 <span data-ttu-id="683a1-105">Para saber mais sobre as funções de nível de banco de dados do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] e suas permissões, consulte [Funções do Integration Services &#40;Serviço SSIS&#41;](security/integration-services-roles-ssis-service.md).</span><span class="sxs-lookup"><span data-stu-id="683a1-105">To learn more about the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] database-level roles and their permissions, see [Integration Services Roles &#40;SSIS Service&#41;](security/integration-services-roles-ssis-service.md).</span></span>  
  
 <span data-ttu-id="683a1-106">As funções listadas na caixa de diálogo são as funções de banco de dados atuais do banco de dados de sistema **msdb** .</span><span class="sxs-lookup"><span data-stu-id="683a1-106">The roles listed in the dialog box are the current database roles of the **msdb** system database.</span></span> <span data-ttu-id="683a1-107">Se nenhuma função for selecionada, serão aplicadas as funções do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="683a1-107">If no roles are selected, the default [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] roles apply.</span></span> <span data-ttu-id="683a1-108">Por padrão, a função de leitor inclui **db_ssisadmin**, **db_ssisoperator**e o usuário que criou o pacote.</span><span class="sxs-lookup"><span data-stu-id="683a1-108">By default, the reader role includes **db_ssisadmin**, **db_ssisoperator**, and the user who created the package.</span></span> <span data-ttu-id="683a1-109">Um usuário membro de uma dessas funções ou criador dos pacotes pode enumerar, exibir, exportar e executar pacotes.</span><span class="sxs-lookup"><span data-stu-id="683a1-109">A user who is a member of one of these roles or created the packages can enumerate, view, export, and run packages.</span></span> <span data-ttu-id="683a1-110">Por padrão, a função de gravador inclui **db_ssisadmin** e o usuário que criou o pacote.</span><span class="sxs-lookup"><span data-stu-id="683a1-110">By default, the writer role includes **db_ssisadmin** and the user who created the package.</span></span> <span data-ttu-id="683a1-111">Um usuário membro dessa função e o criador dos pacotes podem importar, excluir e alterar pacotes.</span><span class="sxs-lookup"><span data-stu-id="683a1-111">A user who is a member of this role and the user who created the packages can import, delete, and change packages.</span></span>  
  
 <span data-ttu-id="683a1-112">A coluna **ownersid** da tabela **sysssispackages** lista o identificador de segurança exclusivo do usuário que criou o pacote.</span><span class="sxs-lookup"><span data-stu-id="683a1-112">The **ownersid** column in the **sysssispackages** table lists the unique security identifier of the user who created the package.</span></span>  
  
## <a name="options"></a><span data-ttu-id="683a1-113">Opções</span><span class="sxs-lookup"><span data-stu-id="683a1-113">Options</span></span>  
 <span data-ttu-id="683a1-114">**Nome do pacote**</span><span class="sxs-lookup"><span data-stu-id="683a1-114">**Package Name**</span></span>  
 <span data-ttu-id="683a1-115">Especifique o nome do pacote.</span><span class="sxs-lookup"><span data-stu-id="683a1-115">Specify the name of the package.</span></span>  
  
 <span data-ttu-id="683a1-116">**Função de leitor**</span><span class="sxs-lookup"><span data-stu-id="683a1-116">**Reader Role**</span></span>  
 <span data-ttu-id="683a1-117">Selecione uma função na lista.</span><span class="sxs-lookup"><span data-stu-id="683a1-117">Select a role in the list.</span></span>  
  
 <span data-ttu-id="683a1-118">**Função de Gravador**</span><span class="sxs-lookup"><span data-stu-id="683a1-118">**Writer Role**</span></span>  
 <span data-ttu-id="683a1-119">Selecione uma função na lista</span><span class="sxs-lookup"><span data-stu-id="683a1-119">Select a role in the list</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="683a1-120">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="683a1-120">See Also</span></span>  
 <span data-ttu-id="683a1-121">[Funções de nível de banco de dados](../relational-databases/security/authentication-access/database-level-roles.md) </span><span class="sxs-lookup"><span data-stu-id="683a1-121">[Database-Level Roles](../relational-databases/security/authentication-access/database-level-roles.md) </span></span>  
 [<span data-ttu-id="683a1-122">Visão geral de segurança &#40;Integration Services&#41;</span><span class="sxs-lookup"><span data-stu-id="683a1-122">Security Overview &#40;Integration Services&#41;</span></span>](security/security-overview-integration-services.md)  
  
  
