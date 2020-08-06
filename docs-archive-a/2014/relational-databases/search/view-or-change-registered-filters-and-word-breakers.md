---
title: Exibir ou alterar filtros registrados e separadores de palavras | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- full-text search [SQL Server], word breakers
- full-text search [SQL Server], filters
- filters [full-text search]
- word breakers [full-text search]
ms.assetid: f88c54df-b1aa-4701-807f-dc92c32363fd
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 79ad7f1f7df15fed21a132bbe253adc7185d8c06
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679823"
---
# <a name="view-or-change-registered-filters-and-word-breakers"></a><span data-ttu-id="52bca-102">Exibir ou alterar filtros registrados e separadores de palavras</span><span class="sxs-lookup"><span data-stu-id="52bca-102">View or Change Registered Filters and Word Breakers</span></span>
  <span data-ttu-id="52bca-103">Depois da instalação ou da desinstalação de qualquer separador de palavras ou de filtros em um sistema, as alterações não entram em vigor automaticamente em instâncias de servidor.</span><span class="sxs-lookup"><span data-stu-id="52bca-103">After any word breakers or filters are installed or uninstalled on a system, the changes do not automatically take effect on server instances.</span></span> <span data-ttu-id="52bca-104">Este tópico descreve como exibir o separador de palavras ou os filtros registrados atualmente, e como registrar separadores de palavras e filtros instalados recentemente em uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="52bca-104">This topic describes how to view the currently registered word breaker or filters and how to register newly installed word breakers and filters on an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
### <a name="to-view-a-list-of-languages-whose-word-breakers-are-currently-registered"></a><span data-ttu-id="52bca-105">Para exibir uma lista de idiomas cujos separadores de palavras estão registrados atualmente</span><span class="sxs-lookup"><span data-stu-id="52bca-105">To view a list of languages whose word breakers are currently registered</span></span>  
  
1.  <span data-ttu-id="52bca-106">Use a exibição de catálogo [sys.fulltext_languages](/sql/relational-databases/system-catalog-views/sys-fulltext-languages-transact-sql) , da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="52bca-106">Use the [sys.fulltext_languages](/sql/relational-databases/system-catalog-views/sys-fulltext-languages-transact-sql) catalog view, as follows:</span></span>  
  
    ```  
    SELECT * FROM sys.fulltext_languages;   
    ```  
  
### <a name="to-view-a-list-of-the-filters-that-are-currently-registered"></a><span data-ttu-id="52bca-107">Para exibir uma lista dos filtros que estão registrados atualmente</span><span class="sxs-lookup"><span data-stu-id="52bca-107">To view a list of the filters that are currently registered</span></span>  
  
1.  <span data-ttu-id="52bca-108">Use o procedimento armazenado do sistema [sp_help_fulltext_system_components](/sql/relational-databases/system-stored-procedures/sp-help-fulltext-system-components-transact-sql) , da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="52bca-108">Use the [sp_help_fulltext_system_components](/sql/relational-databases/system-stored-procedures/sp-help-fulltext-system-components-transact-sql) system stored procedure, as follows:</span></span>  
  
    ```  
    EXEC sp_help_fulltext_system_components 'filter';    
    ```  
  
### <a name="to-register-newly-installed-word-breakers-and-filters"></a><span data-ttu-id="52bca-109">Para registrar separadores de palavras e filtros instalados recentemente</span><span class="sxs-lookup"><span data-stu-id="52bca-109">To register newly installed word breakers and filters</span></span>  
  
1.  <span data-ttu-id="52bca-110">Use o procedimento armazenado do sistema [sp_fulltext_service](/sql/relational-databases/system-stored-procedures/sp-fulltext-service-transact-sql) para atualizar a lista de idiomas, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="52bca-110">Use the [sp_fulltext_service](/sql/relational-databases/system-stored-procedures/sp-fulltext-service-transact-sql) system stored procedure to update the list of languages, as follows:</span></span>  
  
    ```  
    exec sp_fulltext_service 'update_languages';   
    ```  
  
### <a name="to-unregister-uninstalled-word-breakers-and-filters"></a><span data-ttu-id="52bca-111">Para cancelar o registro de separadores de palavras e filtros desinstalados</span><span class="sxs-lookup"><span data-stu-id="52bca-111">To unregister uninstalled word breakers and filters</span></span>  
  
1.  <span data-ttu-id="52bca-112">Use **sp_fulltext_service** para atualizar a lista de idiomas, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="52bca-112">Use the **sp_fulltext_service** to update the list of languages, as follows:</span></span>  
  
    ```  
    exec sp_fulltext_service 'update_languages'  
    ```  
  
2.  <span data-ttu-id="52bca-113">Use **sp_fulltext_service** para reiniciar os processos do host daemon do filtro (fdhost.exe), da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="52bca-113">Use the **sp_fulltext_service** to restart the filter daemon host processes (fdhost.exe), as follows:</span></span>  
  
    ```  
    exec sp_fulltext_service 'restart_all_fdhosts';  
    ```  
  
### <a name="to-replace-existing-word-breakers-or-filters-when-installing-new-ones"></a><span data-ttu-id="52bca-114">Para substituir separadores de palavras ou filtros existentes ao instalar novos</span><span class="sxs-lookup"><span data-stu-id="52bca-114">To replace existing word breakers or filters when installing new ones</span></span>  
  
1.  <span data-ttu-id="52bca-115">Ao preparar a instalação de um arquivo DLL que contém novos separadores de palavras ou filtros, verifique se ele tem um nome de arquivo diferente de qualquer um dos arquivos DLL existentes instalados na instância do servidor.</span><span class="sxs-lookup"><span data-stu-id="52bca-115">When preparing to install a DLL file that contains new word breakers or filters, verify that it has a different filename from any of the existing DLL files installed on your server instance.</span></span>  
  
2.  <span data-ttu-id="52bca-116">Copie o novo arquivo DLL no diretório que contém os arquivos DLL padrão do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para a instância do servidor.</span><span class="sxs-lookup"><span data-stu-id="52bca-116">Copy the new DLL file into the directory containing the standard [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] DLL files for the server instance.</span></span> <span data-ttu-id="52bca-117">O local padrão é:</span><span class="sxs-lookup"><span data-stu-id="52bca-117">The default location is:</span></span>  
  
     <span data-ttu-id="52bca-118">C:\Arquivos de Programas\Microsoft SQL Server\MSSQL.*instance_name*\MSSQL\Binn</span><span class="sxs-lookup"><span data-stu-id="52bca-118">C:\Program Files\Microsoft SQL Server\MSSQL.*instance_name*\MSSQL\Binn</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="52bca-119">É altamente recomendável carregar apenas componentes assinados e verificados.</span><span class="sxs-lookup"><span data-stu-id="52bca-119">We highly recommend that you load only signed and verified components.</span></span> <span data-ttu-id="52bca-120">Além disso, é recomendável executar o Serviço do Iniciador FDHOST (MSSQLFDLauncher) com o mínimo possível de privilégios.</span><span class="sxs-lookup"><span data-stu-id="52bca-120">Also, we recommend that you run the FDHOST Launcher (MSSQLFDLauncher) Service with the least possible privileges.</span></span>  
  
3.  <span data-ttu-id="52bca-121">Instale o novo separador de palavras ou filtros.</span><span class="sxs-lookup"><span data-stu-id="52bca-121">Install the new word breaker or filters.</span></span>  
  
     <span data-ttu-id="52bca-122">**Para instalar e carregar o Microsoft Filter Pack IFilters**</span><span class="sxs-lookup"><span data-stu-id="52bca-122">**To install and load Microsoft Filter Pack IFilters**</span></span>  
  
    -   [<span data-ttu-id="52bca-123">Como registrar o Microsoft Filter Pack IFilters no SQL Server</span><span class="sxs-lookup"><span data-stu-id="52bca-123">How to register Microsoft Filter Pack IFilters with SQL Server</span></span>](https://go.microsoft.com/fwlink/?LinkId=130439)  
  
4.  <span data-ttu-id="52bca-124">Use **sp_fulltext_service** para carregar os separadores de palavras e filtros recentemente instalados na instância de servidor, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="52bca-124">Use **sp_fulltext_service** to load newly installed word breakers and filters in the server instance, as follows:</span></span>  
  
    ```  
    EXEC sp_fulltext_service @action='load_os_resources', @value=1;  
    ```  
  
5.  <span data-ttu-id="52bca-125">Use **sp_fulltext_service** para atualizar a lista de idiomas, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="52bca-125">Use **sp_fulltext_service** to update the list of languages, as follows:</span></span>  
  
    ```  
    EXEC sp_fulltext_service 'update_languages';  
    ```  
  
6.  <span data-ttu-id="52bca-126">Reinicie os processos do host daemon do filtro (fdhost.exe), usando **sp_fulltext_service** da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="52bca-126">Restart the filter daemon host processes (fdhost.exe), using **sp_fulltext_service** as follows:</span></span>  
  
    ```  
    EXEC sp_fulltext_service 'restart_all_fdhosts';   
    ```  
  
## <a name="see-also"></a><span data-ttu-id="52bca-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="52bca-127">See Also</span></span>  
 <span data-ttu-id="52bca-128">[Definir a conta de serviço do Iniciador do Daemon de Filtro de Texto Completo](set-the-service-account-for-the-full-text-filter-daemon-launcher.md) </span><span class="sxs-lookup"><span data-stu-id="52bca-128">[Set the Service Account for the Full-text Filter Daemon Launcher](set-the-service-account-for-the-full-text-filter-daemon-launcher.md) </span></span>  
 <span data-ttu-id="52bca-129">[Configurar e gerenciar filtros para pesquisa](configure-and-manage-filters-for-search.md) </span><span class="sxs-lookup"><span data-stu-id="52bca-129">[Configure and Manage Filters for Search](configure-and-manage-filters-for-search.md) </span></span>  
 [<span data-ttu-id="52bca-130">Configurar e gerenciar separadores de palavras e lematizadores de pesquisa</span><span class="sxs-lookup"><span data-stu-id="52bca-130">Configure and Manage Word Breakers and Stemmers for Search</span></span>](configure-and-manage-word-breakers-and-stemmers-for-search.md)  
  
  
