---
title: Alterar o separador de palavras usado para inglês dos EUA e inglês do Reino Unido | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
ms.assetid: 6b5d2177-db98-47f5-b32e-4b80a2f74ffe
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3b759b90ec834dcb666f7862bfba3857f2fea0d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574623"
---
# <a name="change-the-word-breaker-used-for-us-english-and-uk-english"></a><span data-ttu-id="31fc7-102">Alterar o separador de palavras usado para inglês (EUA) e inglês (Reino Unido)</span><span class="sxs-lookup"><span data-stu-id="31fc7-102">Change the Word Breaker Used for US English and UK English</span></span>
  [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="31fc7-103">instala uma nova versão (versão 14.0.4999.1038) do separador de palavras e lematizador para o idioma inglês, substituindo a versão anterior desses componentes (versão 12.0.6828.0).</span><span class="sxs-lookup"><span data-stu-id="31fc7-103">installs a new version (version 14.0.4999.1038) of the word breaker and stemmer for the English language, replacing the previous version of these components (version 12.0.6828.0).</span></span> <span data-ttu-id="31fc7-104">Para obter informações sobre o comportamento alterado dos novos componentes, veja [Alterações de comportamento na pesquisa de texto completo](full-text-search.md).</span><span class="sxs-lookup"><span data-stu-id="31fc7-104">For information about the changed behavior of the new components, see [Behavior Changes to Full-Text Search](full-text-search.md).</span></span> <span data-ttu-id="31fc7-105">Este tópico descreve como alternar da nova versão desses componentes para a versão anterior, ou alternar da versão anterior para a nova versão.</span><span class="sxs-lookup"><span data-stu-id="31fc7-105">This topic describes how to switch from the new version of these components to the previous version, or to switch back from the previous version to the new version.</span></span> <span data-ttu-id="31fc7-106">Para instalações em cluster, essas alterações devem ser feitas em todos os nós primários e passivos.</span><span class="sxs-lookup"><span data-stu-id="31fc7-106">For cluster installations, these changes should be made on all the primary and passive nodes.</span></span>  
  
 <span data-ttu-id="31fc7-107">As versões anteriores do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usavam separadores de palavras diferentes representados por CLSIDs distintos para o inglês dos EUA (LCID 1033) e o inglês do Reino Unido (LCID 2057).</span><span class="sxs-lookup"><span data-stu-id="31fc7-107">Previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] used different word breakers represented by different CLSIDs for US English (LCID 1033) and UK English (LCID 2057).</span></span> <span data-ttu-id="31fc7-108">Nesta versão, ambos o LCIDs usam os mesmos componentes com os mesmos CLSIDs, como é mostrado na seguinte tabela:</span><span class="sxs-lookup"><span data-stu-id="31fc7-108">In this release, both LCIDs use the same components with the same CLSIDs, as shown in the following table:</span></span>  
  
|<span data-ttu-id="31fc7-109">LCID</span><span class="sxs-lookup"><span data-stu-id="31fc7-109">LCID</span></span>|<span data-ttu-id="31fc7-110">Separador de palavras instalado por versões anteriores</span><span class="sxs-lookup"><span data-stu-id="31fc7-110">Word breaker installed by previous versions</span></span><br /><br /> <span data-ttu-id="31fc7-111">versão 12.0.6828.0</span><span class="sxs-lookup"><span data-stu-id="31fc7-111">version 12.0.6828.0</span></span>|<span data-ttu-id="31fc7-112">Lematizador instalado por versões anteriores</span><span class="sxs-lookup"><span data-stu-id="31fc7-112">Stemmer installed by previous versions</span></span>|<span data-ttu-id="31fc7-113">Separador de palavras instalado por esta versão</span><span class="sxs-lookup"><span data-stu-id="31fc7-113">Word breaker installed by this version</span></span><br /><br /> <span data-ttu-id="31fc7-114">versão 14.0.4999.1038</span><span class="sxs-lookup"><span data-stu-id="31fc7-114">version 14.0.4999.1038</span></span>|<span data-ttu-id="31fc7-115">Lematizador instalado por esta versão</span><span class="sxs-lookup"><span data-stu-id="31fc7-115">Stemmer installed by this version</span></span>|  
|----------|-------------------------------------------------------------------------|--------------------------------------------|-----------------------------------------------------------------------|---------------------------------------|  
|<span data-ttu-id="31fc7-116">1046</span><span class="sxs-lookup"><span data-stu-id="31fc7-116">1033</span></span><br /><span data-ttu-id="31fc7-117">(inglês - EUA)</span><span class="sxs-lookup"><span data-stu-id="31fc7-117">(US English)</span></span>|<span data-ttu-id="31fc7-118">188D6CC5-CB03-4C01-912E-47D21295D77E</span><span class="sxs-lookup"><span data-stu-id="31fc7-118">188D6CC5-CB03-4C01-912E-47D21295D77E</span></span>|<span data-ttu-id="31fc7-119">EEED4C20-7F1B-11CE-BE57-00AA0051FE20</span><span class="sxs-lookup"><span data-stu-id="31fc7-119">EEED4C20-7F1B-11CE-BE57-00AA0051FE20</span></span>|<span data-ttu-id="31fc7-120">9faed859-0b30-4434-ae65-412e14a16fb8</span><span class="sxs-lookup"><span data-stu-id="31fc7-120">9faed859-0b30-4434-ae65-412e14a16fb8</span></span>|<span data-ttu-id="31fc7-121">e1e5ef84-c4a6-4e50-8188-99aef3de2659</span><span class="sxs-lookup"><span data-stu-id="31fc7-121">e1e5ef84-c4a6-4e50-8188-99aef3de2659</span></span>|  
|<span data-ttu-id="31fc7-122">2057</span><span class="sxs-lookup"><span data-stu-id="31fc7-122">2057</span></span><br /><span data-ttu-id="31fc7-123">(inglês - Reino Unido)</span><span class="sxs-lookup"><span data-stu-id="31fc7-123">(UK English)</span></span>|<span data-ttu-id="31fc7-124">173C97E2-AEBE-437C-9445-01B237ABF2F6</span><span class="sxs-lookup"><span data-stu-id="31fc7-124">173C97E2-AEBE-437C-9445-01B237ABF2F6</span></span>|<span data-ttu-id="31fc7-125">D99F7670-7F1A-11CE-BE57-00AA0051FE20</span><span class="sxs-lookup"><span data-stu-id="31fc7-125">D99F7670-7F1A-11CE-BE57-00AA0051FE20</span></span>|<span data-ttu-id="31fc7-126">9faed859-0b30-4434-ae65-412e14a16fb8</span><span class="sxs-lookup"><span data-stu-id="31fc7-126">9faed859-0b30-4434-ae65-412e14a16fb8</span></span>|<span data-ttu-id="31fc7-127">e1e5ef84-c4a6-4e50-8188-99aef3de2659</span><span class="sxs-lookup"><span data-stu-id="31fc7-127">e1e5ef84-c4a6-4e50-8188-99aef3de2659</span></span>|  
  
 <span data-ttu-id="31fc7-128">Os componentes descritos neste tópico são arquivos DLL instalados na pasta `MSSQL\Binn` para a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="31fc7-128">The components described in this topic are DLL files that are installed in the `MSSQL\Binn` folder for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="31fc7-129">O caminho completo geralmente é `C:\Program Files\Microsoft SQL Server\<instance>\MSSQL\Binn`.</span><span class="sxs-lookup"><span data-stu-id="31fc7-129">The full path is typically `C:\Program Files\Microsoft SQL Server\<instance>\MSSQL\Binn`.</span></span>  
  
 <span data-ttu-id="31fc7-130">Para obter mais informações sobre separadores de palavras e lematizadores, veja [Configurar e gerenciar separadores de palavras e lematizadores para pesquisa](configure-and-manage-word-breakers-and-stemmers-for-search.md).</span><span class="sxs-lookup"><span data-stu-id="31fc7-130">For more information about word breakers and stemmers, see [Configure and Manage Word Breakers and Stemmers for Search](configure-and-manage-word-breakers-and-stemmers-for-search.md).</span></span>  
  
## <a name="switching-from-the-current-english-word-breaker-to-the-previous-english-word-breakers"></a><span data-ttu-id="31fc7-131">Alternando do separador de palavras em inglês atual para os separadores de palavras em inglês anteriores</span><span class="sxs-lookup"><span data-stu-id="31fc7-131">Switching from the current English word breaker to the previous English word breakers</span></span>  
  
#### <a name="to-switch-from-the-current-version-of-the-us-english-word-breaker-to-the-previous-version"></a><span data-ttu-id="31fc7-132">Para alternar da versão atual do separador de palavras em inglês dos EUA para a versão anterior</span><span class="sxs-lookup"><span data-stu-id="31fc7-132">To switch from the current version of the US English word breaker to the previous version</span></span>  
  
1.  <span data-ttu-id="31fc7-133">No Registro, navegue até o nó: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<InstanceRoot\>\MSSearch\CLSID**.</span><span class="sxs-lookup"><span data-stu-id="31fc7-133">In the registry, navigate to the following node: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<InstanceRoot\>\MSSearch\CLSID**.</span></span>  
  
2.  <span data-ttu-id="31fc7-134">Use as etapas a seguir para adicionar novas chaves para as ClassIDs COM para o separador de palavras em inglês dos EUA anterior e interfaces de lematizador para LCID 1033:</span><span class="sxs-lookup"><span data-stu-id="31fc7-134">Use the following steps to add new keyS for the COM ClassIDs for the previous US English word breaker and stemmer interfaces for LCID 1033:</span></span>  
  
    1.  <span data-ttu-id="31fc7-135">Adicione uma nova chave com o valor **{188D6CC5-CB03-4C01-912E-47D21295D77E}** ao separador de palavras anterior.</span><span class="sxs-lookup"><span data-stu-id="31fc7-135">Add a new key with the value **{188D6CC5-CB03-4C01-912E-47D21295D77E}** for the previous word breaker.</span></span>  
  
    2.  <span data-ttu-id="31fc7-136">Atualize os dados (Padrão) desse valor de chave para **langwrbk.dll**.</span><span class="sxs-lookup"><span data-stu-id="31fc7-136">Update the (Default) data of that key value to **langwrbk.dll**.</span></span>  
  
    3.  <span data-ttu-id="31fc7-137">Adicione uma nova chave com o valor **{EEED4C20-7F1B-11CE-BE57-00AA0051FE20}** ao lematizador anterior.</span><span class="sxs-lookup"><span data-stu-id="31fc7-137">Add a new key with the value **{EEED4C20-7F1B-11CE-BE57-00AA0051FE20}** for the previous stemmer.</span></span>  
  
    4.  <span data-ttu-id="31fc7-138">Atualize os dados (Padrão) desse valor de chave para **infosoft.dll**.</span><span class="sxs-lookup"><span data-stu-id="31fc7-138">Update the (Default) data of that key value to **infosoft.dll**.</span></span>  
  
3.  <span data-ttu-id="31fc7-139">No Registro, navegue até o seguinte nó: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<InstanceRoot\>\MSSearch\Language\enu**.</span><span class="sxs-lookup"><span data-stu-id="31fc7-139">In the registry, navigate to the following node: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<InstanceRoot\>\MSSearch\Language\enu**.</span></span>  
  
4.  <span data-ttu-id="31fc7-140">Atualize o valor de chave **WBreakerClass** para **{188D6CC5-CB03-4C01-912E-47D21295D77E}** .</span><span class="sxs-lookup"><span data-stu-id="31fc7-140">Update the **WBreakerClass** key value to **{188D6CC5-CB03-4C01-912E-47D21295D77E}**.</span></span>  
  
5.  <span data-ttu-id="31fc7-141">Atualize o valor de chave **StemmerClass** para **{EEED4C20-7F1B-11CE-BE57-00AA0051FE20}** .</span><span class="sxs-lookup"><span data-stu-id="31fc7-141">Update the **StemmerClass** key value to **{EEED4C20-7F1B-11CE-BE57-00AA0051FE20}**.</span></span>  
  
6.  <span data-ttu-id="31fc7-142">Reinicie o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="31fc7-142">Restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
#### <a name="to-switch-from-the-current-version-of-the-uk-english-word-breaker-to-the-previous-version"></a><span data-ttu-id="31fc7-143">Para alternar da versão atual do separador de palavras em inglês do Reino Unido para a versão anterior</span><span class="sxs-lookup"><span data-stu-id="31fc7-143">To switch from the current version of the UK English word breaker to the previous version</span></span>  
  
1.  <span data-ttu-id="31fc7-144">No Registro, navegue até o nó: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<InstanceRoot\>\MSSearch\CLSID**.</span><span class="sxs-lookup"><span data-stu-id="31fc7-144">In the registry, navigate to the following node: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<InstanceRoot\>\MSSearch\CLSID**.</span></span>  
  
2.  <span data-ttu-id="31fc7-145">Use as etapas a seguir para adicionar uma nova chave para as ClassIDs COM para o separador de palavras em inglês do Reino Unido anterior e interfaces de lematizador para LCID 2057:</span><span class="sxs-lookup"><span data-stu-id="31fc7-145">Use the following steps to add a new key for the COM ClassIDs for the previous UK English word breaker and stemmer interfaces for LCID 2057:</span></span>  
  
    1.  <span data-ttu-id="31fc7-146">Adicione uma nova chave com o valor **{173C97E2-AEBE-437C-9445-01B237ABF2F6}** ao separador de palavras anterior.</span><span class="sxs-lookup"><span data-stu-id="31fc7-146">Add a new key with the value **{173C97E2-AEBE-437C-9445-01B237ABF2F6}** for the previous word breaker.</span></span>  
  
    2.  <span data-ttu-id="31fc7-147">Atualize os dados (Padrão) desse valor de chave para **langwrbk.dll**.</span><span class="sxs-lookup"><span data-stu-id="31fc7-147">Update the (Default) data of that key value to **langwrbk.dll**.</span></span>  
  
    3.  <span data-ttu-id="31fc7-148">Adicione uma nova chave com o valor **{D99F7670-7F1A-11CE-BE57-00AA0051FE20}** ao lematizador anterior.</span><span class="sxs-lookup"><span data-stu-id="31fc7-148">Add a new key with the value **{D99F7670-7F1A-11CE-BE57-00AA0051FE20}** for the previous stemmer.</span></span>  
  
    4.  <span data-ttu-id="31fc7-149">Atualize os dados (Padrão) desse valor de chave para **infosoft.dll**.</span><span class="sxs-lookup"><span data-stu-id="31fc7-149">Update the (Default) data of that key value to **infosoft.dll**.</span></span>  
  
3.  <span data-ttu-id="31fc7-150">No Registro, navegue até o seguinte nó: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<InstanceRoot\>\MSSearch\Language\eng**.</span><span class="sxs-lookup"><span data-stu-id="31fc7-150">In the registry, navigate to the following node: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<InstanceRoot\>\MSSearch\Language\eng**.</span></span>  
  
4.  <span data-ttu-id="31fc7-151">Atualize o valor de chave **WBreakerClass** para **{173C97E2-AEBE-437C-9445-01B237ABF2F6}** .</span><span class="sxs-lookup"><span data-stu-id="31fc7-151">Update the **WBreakerClass** key value to **{173C97E2-AEBE-437C-9445-01B237ABF2F6}**.</span></span>  
  
5.  <span data-ttu-id="31fc7-152">Atualize o valor de chave **StemmerClass** para **{D99F7670-7F1A-11CE-BE57-00AA0051FE20}** .</span><span class="sxs-lookup"><span data-stu-id="31fc7-152">Update the **StemmerClass** key value to **{D99F7670-7F1A-11CE-BE57-00AA0051FE20}**.</span></span>  
  
6.  <span data-ttu-id="31fc7-153">Reinicie o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="31fc7-153">Restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="switching-back-from-the-previous-english-word-breakers-to-the-current-english-word-breaker"></a><span data-ttu-id="31fc7-154">Alternando de separadores de palavras em inglês dos EUA anteriores para o separador de palavras em inglês atual</span><span class="sxs-lookup"><span data-stu-id="31fc7-154">Switching back from the previous English word breakers to the current English word breaker</span></span>  
  
#### <a name="to-switch-back-from-the-previous-version-of-the-us-english-word-breaker-to-the-current-version"></a><span data-ttu-id="31fc7-155">Para alternar da versão anterior do separador de palavras em inglês dos EUA para a versão atual</span><span class="sxs-lookup"><span data-stu-id="31fc7-155">To switch back from the previous version of the US English word breaker to the current version</span></span>  
  
1.  <span data-ttu-id="31fc7-156">No Registro, navegue até o nó: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<InstanceRoot\>\MSSearch\CLSID**.</span><span class="sxs-lookup"><span data-stu-id="31fc7-156">In the registry, navigate to the following node: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<InstanceRoot\>\MSSearch\CLSID**.</span></span>  
  
2.  <span data-ttu-id="31fc7-157">Se as chaves a seguir não existirem, use as etapas a seguir para adicionar uma nova chave para as ClassIDs COM para o separador de palavras em inglês dos EUA atual e interfaces de lematizador para LCID 1033:</span><span class="sxs-lookup"><span data-stu-id="31fc7-157">If the following keys do not exist, then use the following steps to add a new key for the COM ClassIDs for the current US English word breaker and stemmer interfaces for LCID 1033:</span></span>  
  
    1.  <span data-ttu-id="31fc7-158">Adicione uma nova chave com o valor **{9faed859-0b30-4434-ae65-412e14a16fb8}** para o separador de palavras atual.</span><span class="sxs-lookup"><span data-stu-id="31fc7-158">Add a new key with the value **{9faed859-0b30-4434-ae65-412e14a16fb8}** for the current word breaker.</span></span>  
  
    2.  <span data-ttu-id="31fc7-159">Atualize os dados (Padrão) desse valor de chave para **MsWb7.dll**.</span><span class="sxs-lookup"><span data-stu-id="31fc7-159">Update the (Default) data of that key value to **MsWb7.dll**.</span></span>  
  
    3.  <span data-ttu-id="31fc7-160">Adicione uma nova chave com o valor **{e1e5ef84-c4a6-4e50-8188-99aef3de2659}** para o lematizador atual.</span><span class="sxs-lookup"><span data-stu-id="31fc7-160">Add a new key with the value **{e1e5ef84-c4a6-4e50-8188-99aef3de2659}** for the current stemmer.</span></span>  
  
    4.  <span data-ttu-id="31fc7-161">Atualize os dados (Padrão) desse valor de chave para **MsWb7.dll**.</span><span class="sxs-lookup"><span data-stu-id="31fc7-161">Update the (Default) data of that key value to **MsWb7.dll**.</span></span>  
  
3.  <span data-ttu-id="31fc7-162">No Registro, navegue até o seguinte nó: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<InstanceRoot\>\MSSearch\Language\eng**.</span><span class="sxs-lookup"><span data-stu-id="31fc7-162">In the registry, navigate to the following node: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<InstanceRoot\>\MSSearch\Language\eng**.</span></span>  
  
4.  <span data-ttu-id="31fc7-163">Atualize o valor de chave **WBreakerClass** para **{9faed859-0b30-4434-ae65-412e14a16fb8}** .</span><span class="sxs-lookup"><span data-stu-id="31fc7-163">Update the **WBreakerClass** key value to **{9faed859-0b30-4434-ae65-412e14a16fb8}**.</span></span>  
  
5.  <span data-ttu-id="31fc7-164">Atualize o valor de chave **StemmerClass** para **{e1e5ef84-c4a6-4e50-8188-99aef3de2659}** .</span><span class="sxs-lookup"><span data-stu-id="31fc7-164">Update the **StemmerClass** key value to **{e1e5ef84-c4a6-4e50-8188-99aef3de2659}**.</span></span>  
  
6.  <span data-ttu-id="31fc7-165">Reinicie o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="31fc7-165">Restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
#### <a name="to-switch-back-from-the-previous-version-of-the-uk-english-word-breaker-to-the-current-version"></a><span data-ttu-id="31fc7-166">Para alternar da versão anterior do separador de palavras em inglês do Reino Unido para a versão atual</span><span class="sxs-lookup"><span data-stu-id="31fc7-166">To switch back from the previous version of the UK English word breaker to the current version</span></span>  
  
1.  <span data-ttu-id="31fc7-167">No Registro, navegue até o nó: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<InstanceRoot\>\MSSearch\CLSID**.</span><span class="sxs-lookup"><span data-stu-id="31fc7-167">In the registry, navigate to the following node: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<InstanceRoot\>\MSSearch\CLSID**.</span></span>  
  
2.  <span data-ttu-id="31fc7-168">Se as chaves a seguir não existirem, use as etapas a seguir para adicionar uma nova chave para as ClassIDs COM para o separador de palavras em inglês do Reino Unido atual e interfaces de lematizador para LCID 2057:</span><span class="sxs-lookup"><span data-stu-id="31fc7-168">If the following keys do not exist, then use the following steps to add a new key for the COM ClassIDs for the current UK English word breaker and stemmer interfaces for LCID 2057:</span></span>  
  
    1.  <span data-ttu-id="31fc7-169">Adicione uma nova chave com o valor **{9faed859-0b30-4434-ae65-412e14a16fb8}** para o separador de palavras atual.</span><span class="sxs-lookup"><span data-stu-id="31fc7-169">Add a new key with the value **{9faed859-0b30-4434-ae65-412e14a16fb8}** for the current word breaker.</span></span>  
  
    2.  <span data-ttu-id="31fc7-170">Atualize os dados (Padrão) desse valor de chave para **MsWb7.dll**.</span><span class="sxs-lookup"><span data-stu-id="31fc7-170">Update the (Default) data of that key value to **MsWb7.dll**.</span></span>  
  
    3.  <span data-ttu-id="31fc7-171">Adicione uma nova chave com o valor **{e1e5ef84-c4a6-4e50-8188-99aef3de2659}** para o lematizador atual.</span><span class="sxs-lookup"><span data-stu-id="31fc7-171">Add a new key with the value **{e1e5ef84-c4a6-4e50-8188-99aef3de2659}** for the current stemmer.</span></span>  
  
    4.  <span data-ttu-id="31fc7-172">Atualize os dados (Padrão) desse valor de chave para **MsWb7.dll**.</span><span class="sxs-lookup"><span data-stu-id="31fc7-172">Update the (Default) data of that key value to **MsWb7.dll**.</span></span>  
  
3.  <span data-ttu-id="31fc7-173">No Registro, navegue até o seguinte nó: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<InstanceRoot\>\MSSearch\Language\eng**.</span><span class="sxs-lookup"><span data-stu-id="31fc7-173">In the registry, navigate to the following node: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<InstanceRoot\>\MSSearch\Language\eng**.</span></span>  
  
4.  <span data-ttu-id="31fc7-174">Atualize o valor de chave **WBreakerClass** para **{9faed859-0b30-4434-ae65-412e14a16fb8}** .</span><span class="sxs-lookup"><span data-stu-id="31fc7-174">Update the **WBreakerClass** key value to **{9faed859-0b30-4434-ae65-412e14a16fb8}**.</span></span>  
  
5.  <span data-ttu-id="31fc7-175">Atualize o valor de chave **StemmerClass** para **{e1e5ef84-c4a6-4e50-8188-99aef3de2659}** .</span><span class="sxs-lookup"><span data-stu-id="31fc7-175">Update the **StemmerClass** key value to **{e1e5ef84-c4a6-4e50-8188-99aef3de2659}**.</span></span>  
  
6.  <span data-ttu-id="31fc7-176">Reinicie o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="31fc7-176">Restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31fc7-177">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="31fc7-177">See Also</span></span>  
 <span data-ttu-id="31fc7-178">[Reverter os separadores de palavras usados por pesquisa à versão anterior](revert-the-word-breakers-used-by-search-to-the-previous-version.md) </span><span class="sxs-lookup"><span data-stu-id="31fc7-178">[Revert the Word Breakers Used by Search to the Previous Version](revert-the-word-breakers-used-by-search-to-the-previous-version.md) </span></span>  
 [<span data-ttu-id="31fc7-179">Alterações de comportamento em pesquisa de texto completo</span><span class="sxs-lookup"><span data-stu-id="31fc7-179">Behavior Changes to Full-Text Search</span></span>](full-text-search.md)  
  
  
