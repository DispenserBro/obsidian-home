<%*
// Получаем доступ к плагинам через API Obsidian
const plugins = app.plugins;

// Собираем информацию о плагинах
let pluginList = "# Список установленных плагинов\n\n";
pluginList += "| Название | Статус |\n";
pluginList += "|----------|--------|\n";

for (const [id, plugin] of Object.entries(plugins.plugins)) {
    const name = plugin.manifest.name || id; // Имя плагина
    const isActive = plugins.enabledPlugins.has(id) ? "Активен" : "Неактивен";
    pluginList += `| ${name} | ${isActive} |\n`;
}

// Добавляем результат в заметку
tR += pluginList;
%>