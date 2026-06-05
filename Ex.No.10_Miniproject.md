## Ex.No: 10 Implementation of 2D Game – Catch Ball in Bowl
## DATE:05-06-2026
## REGISTER NUMBER:212223240083
## AIM:

To develop a simple 2D Catch Ball game in Unity where the player controls a bowl to catch falling balls and earn score points.

## ALGORITHM:
1. Create a new 2D project in Unity.
2. Add game objects: Ball, Bowl, and optional Ground.
3. Attach Rigidbody2D and Collider2D components to Ball.
4. Add BoxCollider2D to Bowl and enable Is Trigger.
5. Create BowlController script to move bowl left and right using input.
6. Create BallFall script to spawn and drop ball using gravity.
7. Create CatchBall script to detect collision using OnTriggerEnter2D.
8. Create ScoreManager script to track and update score.
9. Design UI Canvas and add TextMeshPro for score display.
10. Connect scripts and UI components in Inspector.
11. Run the game and test catching functionality.
## PROGRAM:
BowlController.cs
```
using UnityEngine;

public class BowlController : MonoBehaviour
{
    public float speed = 10f;

    void Update()
    {
        float move = Input.GetAxis("Horizontal");
        transform.position += new Vector3(move * speed * Time.deltaTime, 0, 0);
    }
}
```
 CatchBall.cs
```
using UnityEngine;

public class CatchBall : MonoBehaviour
{
    void OnTriggerEnter2D(Collider2D other)
    {
        if (other.gameObject.name.Contains("Ball"))
        {
            ScoreManager.instance.AddScore(1);
            Destroy(other.gameObject);
        }
    }
}
```
 BallFall.cs
```
using UnityEngine;

public class BallFall : MonoBehaviour
{
    void Start()
    {
        transform.position = new Vector3(Random.Range(-3f, 3f), 5f, 0);
    }
}
```
### Output:
<img width="1919" height="1022" alt="image" src="https://github.com/user-attachments/assets/a939b524-fa9b-414b-a014-1b8bfc88526f" />
<img width="1918" height="971" alt="image" src="https://github.com/user-attachments/assets/f9aed212-e477-4578-a4ce-87bd987177d8" />


### Result:
Thus, the 2D Catch Ball game was successfully developed in Unity and implemented using AI-assisted scripting and game development concepts.
