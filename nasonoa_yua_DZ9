import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

df = pd.read_json('events.json')
df = pd.json_normalize(df['events'])

signature_counts = df['signature'].value_counts()
plt.style.use('ggplot')
fig, ax = plt.subplots(figsize=(12, 8))

sns.barplot(
    x=signature_counts.values,
    y=signature_counts.index,
    ax=ax,
    palette="viridis",
    hue=signature_counts.index,
    legend=False
)

plt.title("Распределение событий безопасности", pad=20, fontsize=16)
plt.xlabel("Количество событий", fontsize=12)
plt.ylabel("Тип события", fontsize=12)
plt.xticks(rotation=45, ha='right')

plt.tight_layout()

plt.savefig('security_plot.png', dpi=150)
# plt.show()
