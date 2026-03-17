---
id: ideq4sdd0gi99ku1
type: NoteCard
createdAt: null
viewedAt: 2026-03-17T13:08:20.219Z
---

# Unity — lab8 - Unity Singleton
Sometimes in Unity, we need to create a class that is instantiated only once. We call this type of class a `singleton`. Typical use cases for singleton classes are scene managers and spawners.

```js
public class GoalManager : MonoBehaviour
{
    public static GoalManager instance = { get; private set; };

    void Awake()
    {
      if (Instance != null)
        {
            Destroy(this);
        }
        else
        {
            Instance = this;
        }
    }

    public void OnInit()
    {
        Debug.Log("[GoalManager:Singleton] init");
    }

    // Accessing methods
    // GoalManager.instance.OnInit();
}
```